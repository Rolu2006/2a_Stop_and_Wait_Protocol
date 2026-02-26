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
## CLIENT.py
```
import socket

with socket.socket() as s:
    s.bind(('localhost', 8000))
    s.listen(5)
    c, addr = s.accept()

    with c:
        while True:
            i = input("Enter data: ")
            c.send(i.encode())

            ack = c.recv(1024).decode()
            if ack:
                print(ack)
            else:
                break
```
## SERVER.py
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    msg = s.recv(1024).decode()
    if not msg:
        break

    print(msg)
    s.send("Acknowledgement Received".encode())
```
## OUTPUT





<img width="1919" height="1137" alt="Screenshot 2026-02-26 144056" src="https://github.com/user-attachments/assets/6e6b5d23-ac6f-4701-8c84-73362474e540" />





## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
