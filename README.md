# TCP_CLIENT.py

import socket
target_host = "# here we put the host name with (www)and the .com"
target_port = 80
# create a socket object
client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
#AF.INET =  parameter is saying we are going to use a standard IPv4 address or hostname
#SOCK_STREAM =  indicates that this will be a TCP client
# connect the client
client.connect((target_host,target_port))
# send some data
client.send(b"GET / HTTP/1.1\r\nHost: here we put the host name with just (.com) without (www)\r\n\r\n")
# receive some data
response = client.recv(4096)
print (response)
