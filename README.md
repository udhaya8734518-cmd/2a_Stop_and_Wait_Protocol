# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
```
Server:
import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Waiting for client...")
c, addr = s.accept()
print("Connected to:", addr)

while True:
    i = input("Enter data: ")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break

Client:
import socket
s = socket.socket()
s.connect(('localhost', 8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```
## OUTPUT
<img width="415" height="268" alt="Screenshot 2026-05-18 134637" src="https://github.com/user-attachments/assets/d0e426d5-b58d-43c5-aa3c-56a6e8515d74" />

<img width="542" height="188" alt="image" src="https://github.com/user-attachments/assets/dadb1953-7a30-4556-8cbd-8cbdf00aa999" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
