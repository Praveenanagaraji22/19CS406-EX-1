# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

### DATE : 09-03-2023

## AIM :
To implement socket programming date and time display from client to server using TCPSockets.


## ALGORITHM :
### SERVER :
### STEP 1: Create a server socket and bind it to port.
### STEP 2: Listen for new connection and when a connection arrives, accept it.
### STEP 3: Send server‟s date and time to the client.
### STEP 4: Read client‟s IP address sent by the client.
### STEP 5: Display the client details.
### STEP 6: Repeat steps 2-5 until the server is terminated.
### STEP 7: Close all streams.
### STEP 8: Close the server socket.
### STEP 9: Stop.
### client :
### STEP 1: Create a client socket and connect it to the server‟s port number.
### STEP 2: Retrieve its own IP address using built-in function.
### STEP 3: Send its address to the server.
### STEP 4: Display the date & time sent by the server.
### STEP 5: Close the input and output streams.
### STEP 6: Close the client socket.
### STEP 7: Stop.


## PROGRAM :
### CLIENT:
Developed By: Praveena N
Reg No: 212222040122
```import socket
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
### SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
print(s.getsockname())
print(s.recv(1024).decode())
s.send("acknowledgement recived from the server".encode())
```







## OUTPUT:
### CLIENT OUTPUT :
![EX-01 CLIENT](https://github.com/Praveenanagaraji22/19CS406-EX-1/assets/119393514/3a4bf71d-d417-45a6-8cd6-10a5f0b7d521)
### SERVER OUTPUT :
![EX-01 SERVER](https://github.com/Praveenanagaraji22/19CS406-EX-1/assets/119393514/5e641ee6-7b52-4dda-bd10-1bbf2c3d6431)




## RESULT :
Thus, the program to implement socket programming date and time display from client to server using TCP Sockets was successfully executed.

