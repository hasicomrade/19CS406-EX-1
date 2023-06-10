# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL
## DATE : 09.03.2023
## AIM :

To write a python program to perform client server model.
## ALGORITHM :

Start the program. Get the frame size from the user To create the frame based on the user request. To send frames to server from the client side. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client. Stop the program
## PROGRAM :
## CLIENT:
```
Developed by : Harshini S
Register Number : 212221220018
import socket
from datetime import datetime
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
print("Client Address : ",addr)
now = datetime.now()
c.send(now.strftime("%d/%m/%Y %H:%M:%S").encode())
ack=c.recv(1024).decode()
if ack:
 print(ack)
 c.close()
```
## SERVER:
```
Developed by :  Amrutha varshni
Register Number : 212222040007
import socket
s=socket.socket()
s.connect(('localhost',8000))
print(s.getsockname())
print(s.recv(1024).decode())
s.send("acknowledgement recived from the server".encode())
```
## OUTPUT:
## CLIENT:
![image](https://github.com/sujathamohankumar/19CS406-EX-1/assets/129851449/05e2f279-4943-4445-9547-958a9edc02fa)


## SERVER:
![image](https://github.com/sujathamohankumar/19CS406-EX-1/assets/129851449/f56e11a8-822d-4896-b112-2ce1c4cf6573)


## RESULT: Thus, python program to perform stop and wait protocol was successfully executed.
