# NU-information-Exchange-System-
Campus Messaging System in C++

This project is a multi-campus messaging system built in C++, leveraging both TCP and UDP protocols. It allows campuses to communicate securely and efficiently in real time. The system demonstrates key concepts in network programming, multi-threading, and client-server architecture.

Features

Authentication: Each campus logs in with a unique name and password. The server validates credentials before allowing communication.

Reliable Messaging with TCP: Messages are delivered reliably between campuses using TCP. The server routes messages based on campus names.

Heartbeat Monitoring with UDP: Clients send periodic UDP heartbeats to inform the server they are online. The server keeps an updated list of active campuses.

Admin Console: Server administrators can broadcast messages to all connected campuses.

Multi-threaded Design: The server handles multiple clients simultaneously, and the client runs multiple threads to manage messaging, heartbeats, and broadcasts concurrently.

Cross-Platform Friendly: Works on Linux with minimal adjustments needed for Windows using Winsock.

System Architecture
Client (Campus)                Server (Central Hub)
-----------------               -----------------
- Console UI                    - Authenticates clients
- TCP connection -> Server      - Routes messages
- UDP heartbeat -> Server       - Maintains active clients list
- Receives TCP messages         - Handles admin console
- Receives UDP broadcasts       - Broadcasts messages


TCP ensures reliable communication for messages.

UDP is used for heartbeat and broadcast messages, making it lightweight and efficient.

Multi-threading allows concurrent handling of multiple clients and messages.

How to Run

Compile the server and client (Linux example):

g++ -std=c++17 server.cpp -o server -pthread
g++ -std=c++17 client.cpp -o client -pthread


Start the server:

./server


Start a client:

./client <CampusName> <Password> <ServerIP>


Example:

./client Lahore NU-LHR-123 127.0.0.1


Client Menu Options:

Send a message to another campus

Quit the client

Admin Commands on Server Console:

broadcast <message> – send a message to all connected campuses

list – view connected campuses and known UDP endpoints

Learning Outcomes

Real-world understanding of TCP vs UDP usage

Multi-threaded programming for concurrent network operations

Client-server architecture design

Handling authentication, message routing, and server broadcasts

LinkedIn One-Paragraph Description

I recently built a multi-campus messaging system in C++ that combines TCP for reliable messaging and UDP for lightweight server notifications. The system allows campuses to authenticate, exchange messages, and receive real-time broadcast updates from administrators. Through this project, I gained hands-on experience in network programming, multi-threading, and client-server architecture, while learning how to integrate multiple communication protocols efficiently for a real-world application.
