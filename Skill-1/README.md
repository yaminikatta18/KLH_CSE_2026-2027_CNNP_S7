# Skill 1: Encapsulation Builder

## Observation Table

| Parameter | TCP Packet | UDP Packet |
| :--- | :--- | :--- |
| Frame Length | [your TCP Frame Length] bytes | 230 bytes |
| Ethernet Header Length | 14 bytes | 14 bytes |
| IP Header Length | 20 bytes | 20 bytes |
| Transport Header Length | [your TCP Header Length] bytes | 8 bytes |
| IP Total Length | [your TCP IP Total Length] bytes | 216 bytes |
| Payload Length | [your TCP Segment Length] bytes | 188 bytes |

## Answers to Questions

1. **What is encapsulation?**
   Encapsulation is the process of wrapping application data with protocol-specific headers (and trailers) as it moves down each layer of the network protocol stack prior to transmission.

2. **What is the purpose of the Ethernet header?**
   The Ethernet (Layer 2) header handles node-to-node delivery on a local area network (LAN) using source and destination MAC addresses and identifies the upper-layer protocol via the EtherType field.

3. **What information is stored in the IP header?**
   The IPv4 (Layer 3) header stores logical addressing and routing fields, including Version, Header Length, Total Length, Identification, Flags, Fragment Offset, TTL, Protocol number, Header Checksum, Source IP, and Destination IP.

4. **What is the difference between TCP and UDP headers?**
   - **TCP Header (20–60 bytes):** Connection-oriented; includes Sequence Numbers, Acknowledgment Numbers, control flags (SYN, ACK, FIN, RST), Window Size, Checksum, and Urgent Pointer.
   - **UDP Header (fixed 8 bytes):** Connectionless; contains only Source Port, Destination Port, Length, and Checksum.

5. **Why does each protocol add a header?**
   Each protocol layer performs a distinct function (port multiplexing, logical routing, physical framing) and requires control metadata so the peer layer on the receiving host can route, validate, and reassemble the data.

6. **What is packet overhead?**
   Packet overhead is the extra non-payload control bytes added by protocol headers and trailers (Ethernet + IP + TCP/UDP) needed to deliver user data.

7. **How does header overhead affect network efficiency?**
   Network efficiency is $(\text{Payload Size} / \text{Total Frame Size}) \times 100$. Higher header overhead reduces the proportion of bandwidth used for actual application data, especially for small payloads.
