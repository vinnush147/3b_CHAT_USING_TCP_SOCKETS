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
```
CLIENT

import socket
s=socket.socket()
s.bind(('localhost',9000))
s.listen(5)
c,addr=s.accept()
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"};
while True:
    ip=c.recv(1024).decode()
    try:
        c.send(address[ip].encode())
    except KeyError:
        c.send("Not Found".encode())

```
```
SERVER

import socket
s=socket.socket()
s.connect(('localhost',9000))
while True:
    ip=input("Enter MAC Address : ")
    s.send(ip.encode())
    print("Logical Address",s.recv(1024).decode())

```
## OUPUT
![Screenshot 2025-04-08 113256](https://github.com/user-attachments/assets/b0edaa38-5896-4f54-ad54-4d4ce067eaf7)
![Screenshot 2025-04-08 113226](https://github.com/user-attachments/assets/a29fe733-4d48-4d71-b309-6552e9a10fb6)

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
