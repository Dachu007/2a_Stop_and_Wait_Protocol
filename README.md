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

Client:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```

Server:

```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```

## OUTPUT

Client:

![Screenshot 2025-04-30 195006](https://github.com/user-attachments/assets/08c3a20b-e78e-4f5a-b0cd-e8fd34993bf9)


Server:

![Screenshot 2025-04-30 195044](https://github.com/user-attachments/assets/4ddd3453-c559-4d61-bee3-a8a4b9222a4f)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
