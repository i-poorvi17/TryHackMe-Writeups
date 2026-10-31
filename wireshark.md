# Wireshark - TryHackMe Notes & Writeup

**Platform:** TryHackMe | **Rooms:** Wireshark: The Basics, Packet Operations, Traffic Analysis
**Tool:** Wireshark | **Category:** Network Traffic Analysis

## Overview
Wireshark is an open-source packet analyser. It captures network traffic, helps investigate live traffic, lets you inspect saved packet captures (pcap files), and breaks each packet down by protocol layer.

## 1. The Interface
- **Packet list:** one row per packet (time, source, destination, protocol, info)
- **Packet details:** the selected packet broken down by layer (Ethernet, IP, TCP, application)
- **Packet bytes:** the raw data in hex

## 2. Capture Filters vs Display Filters
| | Capture filter | Display filter |
|---|---|---|
| When applied | Before capture starts | After capture, on saved data |
| Effect | Packets that don't match are never saved | Hides packets but keeps them in the file |
| Use | Limiting capture size | Day-to-day analysis |

## 3. Display Filters I Practised
| Goal | Filter |
|---|---|
| Traffic to or from one host | `ip.addr == x.x.x.x` |
| One port | `tcp.port == 80` |
| One protocol | `http`, `dns`, `arp`, `icmp` |
| Exclude noise | `!arp` |
| Search packet contents | `frame contains "keyword"` |
| TCP handshake starts (SYN only) | `tcp.flags.syn == 1 && tcp.flags.ack == 0` |

## 4. Useful Features
- **Follow TCP/HTTP stream:** reassembles a conversation into readable form
- **Statistics > Protocol Hierarchy:** which protocols dominate the capture
- **Statistics > Conversations / Endpoints:** who talked to whom, and how much
- **Export objects:** pull files transferred over HTTP out of a capture
- **Apply as filter:** the feature I used most

## 5. Traffic Analysis: What I Practised
- **Stream inspection:** following TCP and HTTP streams exposed a lot of information that helped identify malicious activity.
- **Cleartext protocols:** in unencrypted traffic I could find domain names, usernames and file names, which shows why encryption matters.
- **Name resolution and address traffic:** filtering by protocol made it much easier to find the information I needed.
- **Suspicious items I identified:** zip files, data-transfer techniques, and spam conversations.

## 6. Where I Got Stuck
I got stuck finding the Cobalt Strike server IP address. I solved it by checking suspicious IPs in VirusTotal.

## 7. What I Learned
- Wireshark shows what is actually on the wire, not what an application claims.
- Filtering matters more than capturing: a big capture is useless without good filters.
- Analysing traffic showed me how many details and phases of network activity can be read from a capture.

## Resources
- TryHackMe: Wireshark: The Basics, Packet Operations, Traffic Analysis

---
*Personal learning notes. Room answers and flags are intentionally not included.*