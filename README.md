# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
***echo-server.py:***
~~~
import socket
HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)y:
~~~

***echo-client.py:***
~~~
import socket
HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)
print(f"Received {data!r}")
~~~

## OUTPUT:
***echo-server.py:***

![Screenshot 2025-03-03 204905](https://github.com/user-attachments/assets/599dbe19-a47b-4865-b7f1-03275f434fd5)

***echo-client.py:***

![Screenshot 2025-03-03 204919](https://github.com/user-attachments/assets/558b70c8-d682-4065-99c9-9e5f79dafe56)


## RESULT:
The program is executed successfully
