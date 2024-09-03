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

server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
      print(s.recv(1024).decode())
      s.send("Acknowledgement Recived".encode())

```
client

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
## OUTPUT

![Screenshot 2024-08-27 094126](https://github.com/user-attachments/assets/023c7f92-7a17-4872-8004-7694296960d0)


![Screenshot 2024-08-27 094111](https://github.com/user-attachments/assets/bd2d44d0-ab9b-43cf-95d0-175684320adc)



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
