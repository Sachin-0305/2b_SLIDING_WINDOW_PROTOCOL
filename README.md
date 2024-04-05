# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
```
CLIENT:
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
SERVER:
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
print(s.recv(1024).decode())
s.send("Acknowledgement Recived".encode())
```
## OUPUT
https://private-user-images.githubusercontent.com/150319305/319872424-9e1284e7-cf90-4cf0-aafa-9e5b09a9c1e5.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTIyOTY1NzMsIm5iZiI6MTcxMjI5NjI3MywicGF0aCI6Ii8xNTAzMTkzMDUvMzE5ODcyNDI0LTllMTI4NGU3LWNmOTAtNGNmMC1hYWZhLTllNWIwOWE5YzFlNS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwNDA1JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDQwNVQwNTUxMTNaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1kYWNlZGJmOGIyNGU5YWJmYzE5YTJmNmQ1NzUyYmJlMDRkNzJiZGQ1YWQxMmRiYjUwNmMwZDMyZDgzNmE2MDQ0JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.b4aPm7HAZ2eYgbvbYpBWQam20nxyyoiy0r5pFFml86Y
## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
