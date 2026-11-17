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
## SERVER PROGRAM
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
## CLIENT PRIGRAM
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
<img width="1917" height="1078" alt="Screenshot 2026-11-17 152326" src="https://github.com/user-attachments/assets/18509613-b7c4-4867-baca-8f4fb9cdc89b" />
<img width="1920" height="1080" alt="Screenshot 2026-11-17 152343" src="https://github.com/user-attachments/assets/8bbff41c-ddac-41d5-b7d7-c559bf3cc66c" />
<img width="1917" height="1078" alt="Screenshot 2026-11-17 152352" src="https://github.com/user-attachments/assets/20d5d17e-f4e4-4416-82a6-f3375a0353b0" />
<img width="1915" height="1078" alt="Screenshot 2026-11-17 152424" src="https://github.com/user-attachments/assets/c048af86-2cca-491a-849c-91c2322902ac" />




## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
