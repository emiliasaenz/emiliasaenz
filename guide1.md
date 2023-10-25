# Study Guide: Chapter 1 - Computer Networks: A Systems Approach

## Introduction
Welcome to the study guide for Chapter 1 of the textbook "Computer Networks: A Systems Approach" by Larry Peterson and Bruce Davie. This guide will help you understand the fundamental concepts of computer networks and provide you with questions and exercises to reinforce your understanding. Let's get started!

### Required reading
Sections: 1.1, 1.2, 1.3 and 1.5 

## 1. Building a Scalable Network
- What are the key considerations when building a scalable network?
- Explain the concept of network scalability and why it is important.
- Provide examples of different applications that require a scalable network.
- Why does a network need to be cost-effective, fair, and have robust connectivity?
- Discuss the challenges involved in designing a network that can support various applications.


## 2. Computer Network Architecture
- Define computer network architecture in terms of layers and protocols
- Why are layers and protocols important?
- What is encapsulation, multiplexing and demultiplexing?
- Discuss the role of each layer in the OSI and Internet protocol stack.
- Provide examples of protocols used at each layer of the TCP/IP protocol stack.

## 3. Performance
- Why is important to keep track of the performance of a network?
- What are the main metrics we use to measure network performance?
- Give some examples of the challenges of using different metrics in high speed networks


## Exercises
1. Calculate the total time required to transfer a 1000-KB file in the following cases, assuming an RTT of 50 ms, a packet size of 1 KB data, and an initial 2 × RTT of “handshaking” before data is sent:

    a. The bandwidth is 1.5 Mbps, and data packets can be sent continuously.

    b. The bandwidth is 1.5 Mbps, but after we finish sending each data packet we must wait one RTT before sending the next.
    
    c. The bandwidth is “infinite,” meaning that we take transmit time to be zero, and up to 20 packets can be sent per RTT.
    
    d. The bandwidth is infinite, and during the first RTT we cansend one packet ($2^{1−1}$), during the second RTT we can send two packets ($2^{2−1}$), during the third we can send four ($2^{3−1}$), and so on
    
2. For each of the following operations on a remote file server, discuss whether they are more likely to be delay sensitive or bandwidth sensitive:

    a. Open a file.

    b. Read the contents of a file.
    
    c. List the contents of a directory.
    
    d. Display the attributes of a file.
    
3. Suppose a host has a 1-MB file that is to be sent to another host. The file takes 1 second of CPU time to compress 50% or 2 seconds to compress 60%.

    a. Calculate the bandwidth at which each compression option takes the same total compression + transmission time.
    
    b. Explain why latency does not affect your answer

4. . Discuss the relative performance needs of the following applications in terms of average bandwidth, peak bandwidth, latency, jitter, and loss tolerance:
    
    a. File server.
    
    b. Print server.
    
    c. Digital library.
    
    d. Routine monitoring of remote weather instruments.
    
    e. Voice.
    
    f. Video monitoring of a waiting room.
    
    g. Television broadcasting.


```python

```
