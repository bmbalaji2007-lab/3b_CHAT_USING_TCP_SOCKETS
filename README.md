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
## client
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    msg=input("Client > ") 
    s.send(msg.encode()) 
    print("Server > ",s.recv(1024).decode()) 
```
## server
```
import socket 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    ClientMessage=c.recv(1024).decode() 
    print("Client > ",ClientMessage) 
    msg=input("Server > ") 
    c.send(msg.encode()) 
```
## OUPUT

<img width="1919" height="1018" alt="Screenshot 2026-08-19 084349" src="https://github.com/user-attachments/assets/c4ce7d3b-4311-47db-a651-cbe498b8a497" />

<img width="1919" height="1010" alt="Screenshot 2026-08-19 084454" src="https://github.com/user-attachments/assets/e25544ac-517e-427d-8ab3-630b845f29a2" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.



