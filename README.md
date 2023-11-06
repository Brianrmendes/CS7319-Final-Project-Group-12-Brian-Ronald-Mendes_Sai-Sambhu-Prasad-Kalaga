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
pip install flask flask-socketio transformers sympy matplotlib

Code Editor/IDE:
Choose a code editor or integrated development environment (IDE) for coding. Options include Visual Studio Code, PyCharm, Sublime Text, or your preferred editor.

Project Setup:

Organize your project files, including code, HTML, CSS, and assets, within a project directory.
Running the Application:

**How to compile/Execute:**

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
