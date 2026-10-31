# Wireshark - TryHackMe Notes & Writeup

**Platform:** TryHackMe | **Rooms:** Wireshark: The Basics, Packet Operations, Traffic Analysis
**Tool:** Wireshark | **Category:** Network Traffic Analysis

## Overview
Wireshark is an open-source packet analyser. 
               captures network traffic 
               investigating live traffic
               inspecting packet captures (pcap) 
               breaks each packet down by protocol layer

## 1. The Interface
- **Packet list:** one row per packet (time, source, destination, protocol, info)
- **Packet details:** the selected packet broken down by layer (Ethernet, IP, TCP, application)
- **Packet bytes:** the raw data in hex

## 2. Capture Filters vs Display Filters
| | Capture filter | Display filter |
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
- Especially, 
  My personal most used was Apply display filter.

## 5. Traffic Analysis: What I Practised
- **Scan detection:** when i inspected the packets information through TCP and HTTP stream, it was quite interesting and they consist so many information to identify the malicious things.
- **Cleartext protocols:** in unenrcypted traffic, finding the domain name, username, filename etc was fascinating
- **Name resolution / address traffic:** protocols helps a lot when u filter the packets and also in finding the information
- **Anything suspicious you identified** i identified different type of things like zip files, network data transfer techniques, spam conversations.

## 6. Where I Got Stuck
i was stuck when i was trying to find the cobalt strike server ip address which was done using virustotal tool 

## 7. What I Learned
- Wireshark shows what is actually on the wire, not what an application claims
- Filtering matters more than capturing: a big capture is useless without good filters
- analysing the traffic is soo interesting it shows many other factors, phases of network.
