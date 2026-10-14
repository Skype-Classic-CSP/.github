<h1>Classic Skype Network Protocol</h1>

Classic Skype uses a combination of client-server signaling and peer-to-peer (P2P) networking. Depending on the type of communication and network conditions, Skype can use both TCP and UDP for network traffic.

This documentation explores the networking architecture and protocol behavior of Classic Skype.

In 2012, Microsoft began moving Skype's supernode infrastructure from user-hosted machines to dedicated servers in data centers. This marked a significant change in how the network was managed, while some aspects of Skype's P2P architecture remained in use.

This project investigates Classic Skype protocol implementations across versions 1.4–7.41.
The research follows two development tracks:

Skype 1.4: An experimental server currently supports authentication. Further work will focus on understanding its original peer-to-peer architecture and associated protocols.

Skype 7.36.0.150: The primary development target. Its MSNP24 signaling protocol provides a practical starting point for implementing a test gateway and investigating account initialization and synchronization.

The initial goal is to establish a functioning, interoperable server implementation for the newer client before tackling the additional complexity of earlier Skype networking architectures.
