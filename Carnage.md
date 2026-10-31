# Carnage - TryHackMe (Wireshark Challenge)

**Platform:** TryHackMe | **Category:** Network Traffic Analysis | **Tool:** Wireshark

## Overview
The Challenge was about that there is a person Eric from a company Bartell Ltd who received an email from a known contact when he opened the doc he enabled content accidently and the SOC  department received an alert over it that Eric is making suspicious connections so the pcap was retrieved from the network and handed me for  analysis.

## Objective
To Investigate the packet capture and uncover malicious activites.

## Approach
Walk through your analysis in the order you did it:
1. **First look:**
HTTP protocol filter and date- time method for malicious IP address
2. **Narrowing down:** 
http we used to filter the network  most as we was working on domain names and files shared over network.
3. **Spotting suspicious traffic:** 
the Zip files and Malicious IP address
4. **Following the stream:** 
That files are shared very preciously under the ip address and not always filters who works, sometimes u need to inspect mnaully to find like i inspect like 300 packets one by one to find different domain names.

## Key Wireshark Techniques Used
- Filters- http, dns, smtp, tcp
- Follow TCP/HTTP stream
- Statistics menu (Conversations, Endpoints, Protocol Hierarchy)
- Virus total

## Where I Got Stuck
there was a question about post infected traffic which was very tough to find it took so much time and also there where points when i was lost so yes it was difficult but exciting at same point.

