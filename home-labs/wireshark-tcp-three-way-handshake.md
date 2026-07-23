# Wireshark Home Lab: TCP Three-Way Handshake

## Objective

Learn how TCP establishes a reliable network connection by capturing and analyzing the TCP three-way handshake in Wireshark.

## Environment

- Windows 11
- Wireshark
- Web Browser
- Internet Connection

## Scenario

A web browser established a TCP connection while accessing an HTTP website. The objective was to identify the TCP three-way handshake and understand how a reliable connection is created before application data is exchanged.

## Investigation

A packet capture was performed while visiting a website. The TCP stream was isolated using:

tcp.stream == 5

The first three packets of the stream showed the TCP three-way handshake:

1. SYN
2. SYN, ACK
3. ACK

After the handshake completed, the browser sent an HTTP GET request to retrieve data from the web server.

## Analysis

The TCP handshake ensures that both the client and server can communicate before any application data is transmitted.

The packets observed were:

- SYN – The client requested a connection.
- SYN, ACK – The server acknowledged the request and indicated it was ready.
- ACK – The client confirmed receipt of the server's response.

After the connection was established, HTTP traffic began with a GET request.

The SYN packet contained `Len=0`, indicating that no application data was transmitted during connection establishment.

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

## What I Learned

This lab demonstrated that TCP first establishes a reliable connection before any application data is exchanged.

I also learned that handshake packets contain no application payload (`Len=0`). Only after the handshake completes does the browser begin sending HTTP requests.

## Skills Demonstrated

- Packet Capture
- Wireshark Filtering
- TCP Stream Analysis
- Network Troubleshooting
- TCP Protocol Analysis

## Evidence

tcp-three-way-handshake.png
