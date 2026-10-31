# Carnage - TryHackMe (Wireshark Challenge)

**Platform:** TryHackMe | **Category:** Network Traffic Analysis | **Tool:** Wireshark

## Overview
An employee, Eric at Bartell Ltd, received an email from a known contact and accidentally enabled content when he opened the attached document. The SOC received an alert about suspicious connections from his machine. The packet capture was retrieved from the network and handed over for analysis.

## Objective
Investigate the packet capture and uncover the malicious activity.

## Approach
1. **First look:** I applied the HTTP filter and used date and time to find the malicious IP address.
2. **Narrowing down:** I filtered mostly on HTTP, since the investigation involved domain names and files shared over the network.
3. **Spotting suspicious traffic:** zip files and the malicious IP address stood out.
4. **Following the stream:** filters don't always work. I inspected around 300 packets manually, one by one, to find the different domain names.

## Key Wireshark Techniques Used
- Filters: `http`, `dns`, `smtp`, `tcp`
- Follow TCP/HTTP stream
- Statistics menu (Conversations, Endpoints, Protocol Hierarchy)
- Supporting tool: VirusTotal, to check suspicious IPs and files

## Where I Got Stuck
The question about post-infection traffic was the hardest. It took a long time, and at points I felt lost. It was difficult, but exciting.

## What I Learned
- Filters get you started, but some findings only come from manual packet inspection.
- Analysing a capture means following how an infection progresses, not just spotting one bad packet.
- Wireshark combined with an outside tool like VirusTotal makes an investigation much faster.

## Resources
- TryHackMe: Carnage room
- Video walkthrough I referred to: https://youtu.be/W-GWffKi-Bo

---
*Personal learning notes. Room answers and flags are intentionally not included.*