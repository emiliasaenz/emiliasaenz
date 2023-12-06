# Study Guide: Computer Networking Chapter 5 and Chapter 6



### Required reading
Sections: 5.1, 5.2, 6.1, 6.2, and 6.3

## Computer Networking Study Guide

### End-to-End Protocols

1. What is the purpose of end-to-end protocols in computer networking?
2. Explain the difference between connection-oriented and connectionless protocols.
3. What are the advantages and disadvantages of using end-to-end protocols?
4. How does the Internet Protocol (IP) provide end-to-end delivery?
5. What is the role of the Transport Layer in end-to-end protocols?


### UDP

1. What is UDP and how does it differ from TCP?
2. Explain the advantages and disadvantages of using UDP.
3. How does UDP handle error detection and correction?
4. What are some common applications that use UDP?
5. Discuss the role of ports in UDP communication.



### TCP

1. What is TCP and why is it considered a reliable protocol?
2. Explain the three-way handshake process used by TCP to establish a connection.
3. How does TCP handle flow control and congestion control?
4. Discuss the advantages and disadvantages of using TCP.
5. What are some common applications that rely on TCP for communication?



### Congestion Control

1. What is congestion control and why is it important in computer networks?
2. Discuss the various congestion control algorithms used in TCP.
3. How does TCP react to congestion in the network?
4. What are some techniques used to measure and detect network congestion?


### TCP and Sliding Window


1. What is the sliding window protocol and how does it improve the efficiency of data transmission?
2. Explain the concept of window size in TCP and its impact on network performance.
3. How does TCP handle acknowledgments and retransmissions using the sliding window protocol?
4. Discuss the advantages and disadvantages of using the sliding window protocol.
5. What are some techniques used to optimize the sliding window protocol?



## Exercises

1. Consider a simple UDP-based protocol for requesting files (based somewhat loosely on the Trivial File Transport Protocol, or TFTP). The client sends an initial file request, and the server answers (if the file can be sent) with the first data packet. Client and server then continue with a stop-and-wait transmission mechanism.

    (a) Describe a scenario by which a client might request one file but get another; you may allow the client application to exit abruptly and be restarted with the same port.

    (b) Propose a change in the protocol that will make this situation much less likely.

2. The sequence number field in the TCP header is 32 bits long, which is big enough to cover over 4 billion bytes of data. Even if this many bytes were never transferred over a single connection, why might the sequence number still wrap around from 232 − 1 to 0?

3. The Nagle algorithm, built into most TCP implementations, requires the sender to hold a partial segment’s worth of data (even if PUSHed) until either a full segment accumulates or the most recent outstanding ACK arrives.
    
    (a) Suppose the letters abcdefghi are sent, one per second, over a TCP connection with an RTT of 4.1 seconds. Draw a timeline indicating when each packet is sent and what it contains.
    
    (b) If the above were typed over a full-duplex Telnet connection, what would the user see?

    (c) Suppose that mouse position changes are being sent over the connection. Assuming that multiple position changes are sent each RTT, how would a user perceive the mouse motion with and without the Nagle algorithm?

4. Suppose two hosts A and B are connected via a router R. The A–R link has infinite bandwidth; the R–B link can send one packet per second. R’s queue is infinite. Load is to be measured as the number of packets per second sent from A to B. Sketch the throughput-versus-load and delay-versus-load graphs, or if a graph cannot be drawn, explain why. Would another way to measure load be more appropriate?

5. Suppose that between A and B there is a router R. The A–R bandwidth is infinite (that is, packets are not delayed), but the R–B link introduces a bandwidth delay of 1 packet per second (that is, 2 packets take 2 seconds, etc.). Acknowledgments from B to R, though, are sent instantaneously. A sends data to B over a TCP connection, using slow start but with an arbitrarily large window size. R has a queue size of one, in addition to the packet it is sending. At each second, the sender first processes any arriving ACKs and then responds to any timeouts.

    (a) Assuming a fixed TimeOut period of 2 seconds, what is sent and received for T = 0, 1, . . . , 6 seconds? Is the link ever idle due to timeouts?

    (b) What changes if TimeOut is 3 seconds instead?
