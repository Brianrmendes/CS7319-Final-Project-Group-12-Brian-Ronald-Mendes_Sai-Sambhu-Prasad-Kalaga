# CS7319-Final-Project-Group-12-Brian-Ronald-Mendes_Sai-Sambhu-Prasad-Kalaga
Compilation & Implementation Platform:

Operating System: The Math Chatbot project can be developed and deployed on various operating systems, including Windows, macOS, and Linux.
Programming Language: Python 3.x is the primary programming language used for the project.

Where to Download:
Python: You can download Python from the official website at python.org. Choose the latest stable version available for your operating system.
How to Install and Configure:

Python Installation:

Download: Visit python.org and download the latest version of Python.

Installation: Run the downloaded installer and follow the installation instructions.
Virtual Environment (Optional but Recommended):

Install virtualenv (if not already installed) using pip:
pip install virtualenv

Create a virtual environment for your project (e.g., named 'venv'):
virtualenv venv

Activate the virtual environment:
On Windows:
venv\Scripts\activate
On macOS and Linux:
bash
source venv/bin/activate

Dependencies and Packages:
Install required packages using pip. For example:
pip install flask flask-socketio plotly sympy matplotlib tkinter

Code Editor/IDE:
Choose a code editor or integrated development environment (IDE) for coding. Options include Visual Studio Code, PyCharm, Sublime Text, or your preferred editor.

Project Setup

Organize your project files, including code, HTML, CSS, and assets, within a project directory.
Running the Application:

**How to compile/Execute: (For "Selected" version of the project which is using client server architecture)**

Python Server (server.py) Compilation and Execution:

a. Ensure you have Python installed. If not, you can download it from Python's official website.

b. Install the required Python libraries using pip:

pip install flask sympy plotly

c. Open a terminal or command prompt, navigate to the directory containing server.py, and execute it:

python server.py

This will start your Python server, which listens on a specified port (by default, port 5000).

Node.js Server (server.js) Compilation and Execution:

a. Ensure you have Node.js installed. You can download it from Node.js's official website.

b. Navigate to the directory containing server.js and package.json.

c. Install the required Node.js dependencies by running the following command:
npm install

d. Start the Node.js server:

node server.js

This will start your Node.js server, which listens on port 3000 by default.

HTML and JavaScript in the Browser:

You don't need to compile HTML and JavaScript files explicitly. The HTML file (index.html) and JavaScript file (script.js) are served directly to the client's web browser.
To view the chatbot application, open your web browser and navigate to http://localhost:3000 (or the appropriate URL for your Node.js server).
Now, you should have both the Python and Node.js servers running, serving the web-based chatbot application to clients.

**How to complie and execute P2P version:**
1. Install python (Latest version: Optional)
2. Make sure you installed the following packages: TKinter, socket, threading, and sympy
3. Run the .py file
4. You will be asked to select the mode
5. choose "Chatbot Mode first time. It will be waiting for connection..
6. Now split the terminal and run the code again (Or your chose to run the code but the first execution should stay intact)
7. This time choose peer mode. And you iwll be asked to enter the IP Address of your present internet connection
8. Once entered, you are ready to chat with the chatbot get answers for your mathematical queries

**Difference between architectural designs**

Client-Server Architecture:

Design Overview: In the client-server architecture, the system is divided into two main components: clients and servers. Clients initiate requests for services, while servers process these requests and return results. This design creates a clear separation of concerns.

Communication: Clients and servers communicate over a network, typically using protocols like HTTP, WebSocket, or custom communication protocols. The server listens for incoming requests and responds accordingly.

Rationale: This architecture is suitable for systems where centralized control, scalability, reliability, and security are essential. It allows for efficient management of resources and security policies. Scalability is achieved by adding more servers as needed.

Peer-to-Peer (P2P) Architecture:

Design Overview: In a P2P architecture, there is no clear distinction between clients and servers. All nodes in the network can act both as consumers and providers of services. Each node can initiate requests or respond to requests from other nodes.

Communication: Communication in a P2P system is decentralized, with nodes directly communicating with each other. There is no central server to process requests. Instead, nodes collaborate to provide services.

Rationale: P2P architecture is suitable for applications where nodes have equal importance and can share resources. It is often used in file-sharing applications and decentralized networks. However, it can be challenging to manage security, data consistency, and centralized control in a P2P system.

Rationale for Final Selection (Client-Server Architecture):

The rationale for selecting the client-server architecture in the Math Chatbot project is as follows:

Centralized Control: The client-server architecture allows for centralized control and management of resources, making it easier to enforce security policies, data consistency, and access control. This is crucial for our project, which deals with sensitive information, such as mathematical computations.

Scalability: Client-server systems are typically more scalable. We can add more clients and servers to meet increasing demand, and servers can be specialized for specific tasks. This scalability is important as our project may experience varying workloads.

Reliability: Servers in the client-server architecture can be designed for high availability and redundancy. In case one server goes down, another can take over, ensuring continuous service. This high reliability is essential for uninterrupted user interactions.

Security: The client-server architecture allows for the implementation of robust security measures. Security protocols can be enforced on the server side, which is particularly important when handling user data and complex mathematical calculations.

In summary, the client-server architecture aligns with the needs of our project, providing centralized control, scalability, reliability, and robust security, which are essential for a mathematical chatbot system handling sensitive information and serving users effectively.

Comparison and Evaluation of Pros and Cons for Both Architectures:

Client-Server Architecture Pros:

Centralized Control,
Scalability,
Reliability,
Security,

P2P Architecture Pros:

Decentralization,
Equal Node Importance,
Distributed Load

Client-Server Architecture Cons:

Central Point of Failure (Server),
Maintenance Overhead,
Initial Setup Complexity

P2P Architecture Cons:

Security Challenges,
Data Consistency,
Limited Centralized Control.

