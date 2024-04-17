# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
```
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
## OUPUT - ARP
![2c 1](https://github.com/KavinilavanDK/2c.ARP_RARP_PROTOCOLS/assets/144870429/3b9ab262-9885-479b-ac0e-5aa2502acdb8)

## PROGRAM - RARP

```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 ip=input("Enter logical Address : ")
 s.send(ip.encode())
 print("MAC Address",s.recv(1024).decode())
```
## OUPUT -RARP
![2c 2](https://github.com/KavinilavanDK/2c.ARP_RARP_PROTOCOLS/assets/144870429/25441985-2a1b-4014-a3dd-e6c90e4f88c4)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
