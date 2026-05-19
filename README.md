# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
### Server.py
```
import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Server waiting for connection...")
c, addr = s.accept()
print("Connected to:", addr)
while True:
    ClientMessage = c.recv(1024).decode()
    if not ClientMessage:
        break
    print("Client >", ClientMessage)
    c.send(ClientMessage.encode())
c.close()
```
### Client.py
```
import socket
s = socket.socket()
s.connect(('localhost', 8000))
while True:
    msg = input("Client > ")
    s.send(msg.encode())
    print("Server >", s.recv(1024).decode())
```
## OUTPUT
### Server Side:
<img width="1492" height="951" alt="image" src="https://github.com/user-attachments/assets/480b1484-666b-40d4-bfa2-36d4f0824ac2" />

### Client side:
<img width="1494" height="952" alt="image" src="https://github.com/user-attachments/assets/db051753-7f23-470a-8cde-f8282f392cc8" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
