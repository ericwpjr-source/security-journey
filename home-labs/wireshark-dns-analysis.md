# Wireshark Home Lab: DNS Traffic Analysis

## Objective

Capture and analyze DNS traffic using Wireshark to understand how a computer resolves a domain name into an IP address.

## Environment

- Windows 11
- Wireshark
- Wi-Fi connection

## Scenario

I captured network traffic while browsing the web to observe how my computer communicates with a DNS server.

## Investigation

During the packet capture, I identified both DNS queries and DNS responses.

The computer sent a DNS query requesting the IPv4 address (A record) for `clientservices.googleapis.com`.

The DNS server successfully responded with the IPv4 address:

`142.251.219.174`

The capture also showed an AAAA query, which requests the IPv6 address for the same domain.

## Findings

- DNS queries request IP addresses for domain names.
- A records return IPv4 addresses.
- AAAA records return IPv6 addresses.
- A successful DNS response indicates that DNS resolution is functioning correctly.

## What I Learned

This lab helped me understand how DNS works and how to identify DNS traffic in Wireshark. I learned how to distinguish between DNS queries and responses and how to determine whether DNS successfully resolved a domain name.

## Skills Demonstrated

- Wireshark packet analysis
- DNS troubleshooting
- Identifying A and AAAA records
- Basic network traffic analysis

## Evidence

![DNS Query and Response](../images/dns-query-response-highlighted.png)

*Figure 1: Wireshark capture showing a DNS query (Packet 8) and the corresponding DNS response (Packet 13). The computer requested the IPv4 address (A record) for `clientservices.googleapis.com`, and the DNS server returned the IPv4 address `142.251.219.174`, confirming successful DNS resolution.*
