**Definition:** TCP is a connection-oriented, reliable, and byte-stream-oriented communication protocol used for transmitting data across networks.

**Characteristics:**
    - **Reliability:** TCP ensures reliable delivery of data by using acknowledgments, sequence numbers, and retransmissions. It guarantees that data is delivered correctly and in the correct order.
    - **Connection-Oriented:** TCP establishes a connection between a client and a server before data exchange. This connection setup involves a three-way handshake to negotiate parameters and synchronize sequence numbers.
    - **Flow Control:** TCP implements flow control mechanisms to regulate the rate of data transmission based on the receiver's ability to process data. It prevents overwhelming the receiver with a flood of data.
    - **Congestion Control:** TCP dynamically adjusts its transmission rate in response to network congestion to maintain optimal performance and prevent packet loss.

**Three-Way Handshake:**
    - **SYN (Synchronise):** The client sends a SYN packet to the server to initiate a connection request. The SYN packet contains an initial sequence number.
    - **SYN-ACK (Synchronise-Acknowledgment):** Upon receiving the SYN packet, the server responds with a SYN-ACK packet. The SYN-ACK packet acknowledges the client's SYN and contains the server's own initial sequence number.
    - **ACK (Acknowledgment):** Finally, the client sends an ACK packet to acknowledge the server's SYN-ACK. This completes the three-way handshake, and the connection is established.

**Usage:** TCP is commonly used for applications that require reliable, ordered, and error-checked delivery of data, such as web browsing, email transfer (SMTP), file transfer (FTP), and remote terminal access (SSH).


See also:
- [[Networking]]
- [[User Datagram Protocol (UDP)]]
- [[Remote Terminal Access (SSH)]]
- [[File Transfer Protocol (FTP)]]