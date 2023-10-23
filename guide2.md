# Study Guide: Computer Networking Chapter 2


### Required reading
Sections: 2.1, 2.2, 2.4, 2.5, 2.6 and 2.7 

## Technology perspective

1. What are the different technologies used for connecting nodes in a computer network?

## Encoding

1. What is encoding in the context of computer networking?
2. Explain the difference between analog and digital signals.
3. Explain the different types of encoding used in computer networks


## Error Detection

1. What is error detection and why is it important in computer networks?
2. Explain the concept of parity checking for error detection.
3. Discuss the advantages and limitations of parity checking.
4. Describe the process of using checksums for error detection.
5. Explain Cyclic Redundancy checks. 

## Reliable Transmission

1. What is reliable transmission and why is it important in computer networks?
2. Explain the concept of stop-and-wait protocol for reliable transmission.
3. Discuss the advantages and limitations of stop-and-wait protocol.
4. Describe the process of using sliding window protocol for reliable transmission.

## Ethernet and Multiple Access Networks

1. What is Ethernet and how does it work?
2. Explain the concept of multiple access networks.
3. Discuss the advantages and limitations of Ethernet.
4. Describe the process of collision detection in Ethernet.
5. Give examples of different multiple access techniques used in computer networks.

## Wireless Networks

1. What are wireless networks and how do they work?
2. Explain the concept of wireless communication channels.
3. Discuss the advantages and limitations of wireless networks.
4. Describe the process of wireless signal propagation and interference.
5. Give examples of different wireless networking technologies used in computer networks.

## Exercises

1. Show the Manchester, 4B/5B encoding, and the resulting NRZI signal, for the
following bit sequence:
1110 0101 0000 0011

2. Show the Manchester, 4B/5B encoding, and the resulting NRZI signal, for the
following bit sequence:
1101 1110 1010 1101 1011 1110 1110 1111

3. Suppose we want to transmit the message "1011 0010 0100 1011" and protect it from errors using the CRC8 polynomial $x^8 + x^2 + x^1 + 1$.

- Use polynomial long division to determine the message that should be transmitted.
- Suppose the leftmost bit of the message is inverted due to noise on the transmission link. What is the result of the receiver’s CRC calculation? How does the receiver know that an error has occurred?

4. Consider an ARQ protocol that uses only negative acknowledgments (NAKs), but no positive acknowledgments (ACKs). Describe what timeouts would have to be scheduled. Explain why an ACK-based protocol is usually preferred to a NAK-based protocol.


5. Draw a timeline diagram for the sliding window algorithm with SWS = RWS = 3 frames, for the following two situations. Use a timeout interval of about 2 × RTT.

- Frame 4 is lost.
- Frames 4 to 6 are lost.