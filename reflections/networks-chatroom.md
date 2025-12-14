# Networks Chatroom

**Repository:** https://github.com/lmorgenthaler/networks-chatroom

## Reflective Summary

This project is a multi-client chatroom application developed as part of my Networks and Security coursework. 
The system consists of a server and multiple clients that communicate using a custom binary KLV (Key-Length-Value) protocol. 
The server handles concurrent client connections, message broadcasting, and message storage using a lightweight SQLite database. 
This project required careful attention to protocol design, socket programming, concurrency, and data serialization, 
as well as debugging real-world networking edge cases and common issues such as partial reads, synchronization, 
and graceful client disconnects.

I chose this project for my portfolio because it challenged me to think beyond application-level logic 
and work closer to the networking layer, where mistakes have greater consequences and require precise reasoning. 
Designing my own protocol forced me to think critically about how data is structured, transmitted, and interpreted 
across distributed systems. This project directly correlates with the Computer Science learning goals of problem solving,
systems-level thinking, and applying theoretical concepts in a practical context. It also aligns with Westminster’s Critical Thinking, 
Communication, and Collaboration learning goals.

## Learning Goals Addressed
- Computer Science: Networking fundamentals, concurrency, systems programming
- Critical Thinking
- Communication
- Collaboration
