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
### CILENT
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
### SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
### CILENT
![2A cilent img](https://github.com/Alfredsec/2a_Stop_and_Wait_Protocol/assets/120621608/015f4a4d-b933-47cd-8905-007e22b9829f)

### SERVER
![2A server img](https://github.com/Alfredsec/2a_Stop_and_Wait_Protocol/assets/120621608/cfaf2e6f-903d-46b2-a281-fa3090c3883a)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
