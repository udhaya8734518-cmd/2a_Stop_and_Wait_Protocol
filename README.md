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
Client:
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

Server:
import socket
s = socket.socket()
s.connect(('localhost', 8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```
## OUTPUT
<img width="673" height="141" alt="image" src="https://github.com/user-attachments/assets/447217f2-e397-45e1-941f-3f8fca929026" />

<img width="700" height="329" alt="image" src="https://github.com/user-attachments/assets/e4364e1a-690c-4303-9e92-b7568f625144" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
