# NU-information-Exchange-System-
A  campus messaging system built in C++ that combines TCP and UDP protocols for reliable communication and real-time notifications. Perfect for learning network programming, multi-threading, and building a scalable messaging server.

About

This project simulates a simple campus communication network. The server acts as the central hub, handling authentication, message routing, and broadcast notifications. Each client represents a campus that can send messages to other campuses and receive real-time updates.

The system demonstrates how TCP can be used for reliable messaging, while UDP handles lightweight heartbeats and broadcast messages efficiently.

Features

Secure Authentication: Campuses log in with unique credentials before sending messages.

Reliable Messaging with TCP: Messages are routed safely and reliably between campuses.

Heartbeat Monitoring with UDP: Clients send periodic signals so the server knows who is online.

Admin Console: Broadcast messages to all connected campuses and view active clients.

Multi-threaded Design: Clients and server can handle multiple tasks simultaneously.

How it Works

Server: Listens for TCP connections, authenticates clients, keeps track of TCP sockets and UDP addresses. Routes messages between campuses and allows admins to broadcast messages to all clients.

Client: Connects to the server using TCP, authenticates, and runs three threads for:

Listening for TCP messages

Sending periodic UDP heartbeats

Receiving UDP broadcast messages

Users interact via a simple console menu to send messages or quit.
Compile Server:
g++ -std=c++17 server.cpp -o server -pthread
./server
Compile Client:
g++ -std=c++17 client.cpp -o client -pthread
./client <CampusName> <Password> <ServerIP>
Learning Outcomes

Understanding TCP vs UDP communication and when to use each

Multi-threaded application design

Building a scalable server capable of handling multiple clients

Real-world experience with sockets and network programming in C++

Future Improvements

Persistent message queues for offline campuses

GUI client for better user interaction

Encryption for secure message transmission

Logging and analytics for server activity

