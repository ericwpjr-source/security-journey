# Wireshark Home Lab: TCP Three-Way Handshake

## Objective

Learn how TCP establishes a reliable network connection by capturing and analyzing the TCP three-way handshake in Wireshark.

---

## Environment

- Windows 10
- Wireshark
- Web Browser
- Internet Connection

---

## Scenario

A packet capture was performed while accessing an HTTP website. The objective was to identify the TCP three-way handshake and understand how a reliable connection is established before application data is exchanged.

---

## Investigation

A packet capture was performed while browsing to an HTTP website. After capturing the traffic, the TCP conversation was isolated using the following Wireshark display filter:

```text
tcp.stream == 5
```

The first three packets in the stream showed the TCP three-way handshake:

1. SYN
2. SYN, ACK
3. ACK

After the handshake completed, the browser sent an HTTP GET request to retrieve data from the web server.

---

## Analysis

TCP establishes a reliable connection before transmitting application data.

The packets observed were:

- **SYN** – The client requested to establish a connection with the server.
- **SYN, ACK** – The server acknowledged the request and indicated it was ready to communicate.
- **ACK** – The client confirmed receipt of the server's response.

During the handshake, all three packets contained `Len=0`, indicating that no application data was exchanged while the connection was being established.

After the handshake completed, the browser transmitted an HTTP GET request over the established connection.

This capture also demonstrated communication over **IPv6**, showing that the TCP three-way handshake functions the same way regardless of whether IPv4 or IPv6 is used.

---

## Key Concepts

- TCP
- Three-Way Handshake
- SYN
- SYN-ACK
- ACK
- Source Port
- Destination Port
- HTTP
- Port 80
- IPv6

---

## What I Learned

This lab helped me understand how TCP creates a reliable connection before any application data is exchanged.

I learned that:

- The TCP handshake consists of three packets: SYN, SYN-ACK, and ACK.
- Handshake packets contain no application payload (`Len=0`).
- After the handshake completes, the client begins transmitting HTTP requests.
- TCP behaves the same whether it is running over IPv4 or IPv6.

---

## Skills Demonstrated

- Packet Capture
- Wireshark Display Filters
- TCP Stream Analysis
- Network Traffic Analysis
- Basic Network Troubleshooting
- Protocol Identification

---

## Evidence

![TCP Three-Way Handshake](../images/tcp-three-way-handshake.png)

The screenshot below shows the TCP three-way handshake captured in Wireshark.

- Packet 1: SYN
- Packet 2: SYN, ACK
- Packet 3: ACK
