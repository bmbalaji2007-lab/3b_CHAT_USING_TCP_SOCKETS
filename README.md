# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
## Server Program:
```
import socket 

server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM) 

host = '127.0.0.1' 
port = 5000 
server_socket.bind((host, port)) # Listen for client 
server_socket.listen(1)
print("Waiting for client connection...")  
client_socket, addr = server_socket.accept() 
print("Connected to:", addr)
while True: # Receive message from client 
    client_message = client_socket.recv(1024).decode() 
    print("Client:", client_message)  
    if client_message.lower() == "bye": 
        break # Send message to client 
    message = input("Server: ") 
    client_socket.send(message.encode()) 
    if message.lower() == "bye": 
        break 
client_socket.close()
server_socket.close() 
```

## Client Program:
```
import socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM) # Server details 
host = '127.0.0.1' 
port = 5000 # Connect to server 
client_socket.connect((host, port)) 
print("Connected to server")
while True:  
    message = input("Client: ")
    client_socket.send(message.encode()) 
    if message.lower() == "bye": 
        break  
    server_message = client_socket.recv(1024).decode() 
    print("Server:", server_message) 
    if server_message.lower() == "bye":
        break # Close connection 
client_socket.close() 
```
## OUPUT
<img width="1567" height="358" alt="image" src="https://github.com/user-attachments/assets/f0436f2b-c3b4-4383-b798-1b1b233773ef" />

<img width="1538" height="445" alt="image" src="https://github.com/user-attachments/assets/e770dca3-348b-4448-b7ff-dfaf882591fd" />


## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
