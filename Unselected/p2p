import tkinter as tk
from tkinter import ttk
import socket
import threading
import sympy as sp
from tkinter import simpledialog, font

x = sp.symbols('x')

def chatbot_response(text):
    if "hello" in text:
        return "Hi there!"
    elif "how are you" in text:
        return "I'm just a computer program, so I don't have feelings, but I'm functioning correctly!"
    else:
        try:
            if "solve" in text:
                eq_text = text.split("solve(")[1].split(",")[0]
                equation = sp.sympify(eq_text)
                result = sp.solve(equation, x)
            else:
                expr = sp.sympify(text)
                result = sp.simplify(expr)
            return str(result)
        except:
            return "Sorry, I couldn't understand or solve that mathematical expression."

def handle_peer(conn, output_text):
    while True:
        data = conn.recv(1024)
        if not data:
            break
        response = chatbot_response(data.decode("utf-8"))
        output_text.insert(tk.END, f"Peer: {data.decode('utf-8')}\n")
        output_text.insert(tk.END, f"Chatbot: {response}\n")
        conn.sendall(response.encode("utf-8"))
    conn.close()

class App:
    def __init__(self, master):
        self.master = master
        self.master.title("P2P Chatbot")
        self.master.configure(bg="#282c34")

        my_font = font.nametofont("TkDefaultFont").copy()
        my_font.actual()['size'] = 14

        self.label = tk.Label(master, text="Choose Mode", bg="#282c34", fg="#ffffff", font=my_font)
        self.label.pack(pady=20)

        self.chatbot_button = ttk.Button(master, text="Start as Chatbot", command=self.start_chatbot_ui)
        self.chatbot_button.pack()

        self.peer_button = ttk.Button(master, text="Start as Peer", command=self.start_peer_ui)
        self.peer_button.pack(pady=20)

    def start_chatbot_ui(self):
        self.master.withdraw()
        chatbot_window = tk.Toplevel(self.master)
        chatbot_window.title("Chatbot Mode")
        chatbot_window.configure(bg="#282c34")

        self.output_text = tk.Text(chatbot_window, height=20, width=50, bg="#333842", fg="#ffffff")
        self.output_text.pack(pady=20, padx=20)

        threading.Thread(target=self.start_chatbot, args=(self.output_text,)).start()

    def start_chatbot(self, output_text):
        HOST = "0.0.0.0"
        PORT = 65432

        with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
            s.bind((HOST, PORT))
            s.listen()
            output_text.insert(tk.END, "Listening for incoming connections...\n")
            conn, addr = s.accept()
            output_text.insert(tk.END, f"Connected to {addr}\n")
            handle_peer(conn, output_text)

    def start_peer_ui(self):
        self.master.withdraw()
        peer_window = tk.Toplevel(self.master)
        peer_window.title("Peer Mode")
        peer_window.configure(bg="#282c34")

        self.output_text_peer = tk.Text(peer_window, height=20, width=50, bg="#333842", fg="#ffffff")
        self.output_text_peer.pack(pady=20, padx=20)

        entry_frame = tk.Frame(peer_window, bg="#282c34")
        entry_frame.pack(pady=10)

        self.peer_entry = tk.Entry(entry_frame, width=40)
        self.peer_entry.pack(side=tk.LEFT)
        self.peer_entry.bind('<Return>', lambda event=None: self.send_message_to_chatbot())

        send_button = ttk.Button(entry_frame, text="Send", command=self.send_message_to_chatbot)
        send_button.pack(side=tk.LEFT, padx=5)

        peer_ip = simpledialog.askstring("Input", "Enter the IP address of the chatbot:")
        threading.Thread(target=self.start_peer, args=(peer_ip, self.output_text_peer)).start()

    def start_peer(self, peer_ip, output_text_peer):
        PORT = 65432
        self.peer_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        self.peer_socket.connect((peer_ip, PORT))

        threading.Thread(target=self.listen_to_chatbot, args=(self.peer_socket, output_text_peer)).start()

    def listen_to_chatbot(self, s, output_text_peer):
        while True:
            data = s.recv(1024)
            if not data:
                break
            output_text_peer.insert(tk.END, f"Chatbot: {data.decode('utf-8')}\n")

    def send_message_to_chatbot(self):
       message = self.peer_entry.get()
       self.output_text_peer.insert(tk.END, f"You: {message}\n")
       self.peer_socket.sendall(message.encode("utf-8"))
       self.peer_entry.delete(0, tk.END)

root = tk.Tk()
app = App(root)
root.mainloop()
