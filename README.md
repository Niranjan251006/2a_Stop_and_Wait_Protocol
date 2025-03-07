# EX 2a_Stop_and_Wait_Protocol
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
DEVOLPED BY : NIRANJAN S
REG NO: 24900209

Client:
~~~
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
~~~

Server:
~~~
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
   print(s.recv(1024).decode())
   s.send("Acknowledgement Recived".encode())
~~~
## OUTPUT
![359334297-857c12cf-c63a-4af5-a11c-26f65d0feb6b](https://github.com/user-attachments/assets/d646f606-5adb-4291-8d63-ac3b4887b2fd)
![359334307-3206401b-0000-4408-b1f8-5cca4754066c](https://github.com/user-attachments/assets/cfb89b9f-1759-4117-8b95-9541cc0891cc)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
