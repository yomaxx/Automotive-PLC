TwinCAT_TCP_IP_Server

A function block for receiving and sending data using TF6310 TwinCAT TCP/IP Server.

Usage
Install TwinCAT
Install Python3.
Run the TwinCAT server program first.
Run the client Python program.
See commands.md for the available commands. TwinCAT will echo back all commands.

How it works
What's happening inside the function block FB_TcpServer:

The function block FB_SocketConnect will open the socket at the specific port (in our example port:24100).
Python client will then need to connect to the host and the port.
Every half a second, FB_SocketAccept will accept any incoming connection, and populate the variable 'hSocket' with the local address of the server and remote address of the client.
The server program also expects a command from the client every 200ms, if no command is received in 200ms it is considered as disconnected.

The function block FB_SocketSend and FB_SocketReceive use this 'hSocket' variable to send and receive data.
State machine


