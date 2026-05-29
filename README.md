# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
## SERVER:
```
import socket 
# Create socket 
server = socket.socket() 
# Bind IP and port 
server.bind(("127.0.0.1", 5555)) 
# Listen for client 
server.listen(1) 
print("Server waiting for connection...") 
# Accept client 
client, addr = server.accept() 
print("Connected to:", addr) 
# Ask filename 
filename = input("Enter file name to send: ") 
# Open and send file 
with open(filename, "rb") as file: 
    data = file.read() 
    client.send(data) 
print("File sent successfully") 
# Close connections 
client.close() 
server.close()
```
## CLIENT:
```
import socket 
# Create socket 
client = socket.socket() 
# Connect to server 
client.connect(("127.0.0.1", 5555)) 
# Save file name 
save_name = input("Enter name to save file: ") 
# Receive data 
data = client.recv(1000000) 
# Save file 
with open(save_name, "wb") as file: 
    file.write(data) 
print("File received successfully") 
# Close connection 
client.close()
```


## OUPUT
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e3d40272-7d6a-40de-ae67-93d66cb8114e" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6f2b25ca-f8ea-445f-98f4-528af150871a" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/74ac3eeb-2776-4690-88a3-6ef7f23b1249" />
<img width="1758" height="894" alt="image" src="https://github.com/user-attachments/assets/68788579-c70d-405c-814c-bf920b7c93e0" />


## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
