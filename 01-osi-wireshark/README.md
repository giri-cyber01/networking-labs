# OSI Model Analysis Using Wireshark

## 1. Overview

This lab explores how the OSI (Open Systems Interconnection) model relates to real network traffic.

I used Wireshark to capture network packets and inspect the protocol headers of a selected packet. The objective was to connect networking theory with practical packet analysis.

## 2. Objectives

- Capture network traffic from my own device.
- Identify the protocol headers visible in a selected packet.
- Map the observed protocols and fields to the appropriate OSI layers.
- Understand the roles of MAC addresses, IP addresses, and TCP/UDP ports.
- Document observations and explain the limitations of packet analysis.

## 3. Tools and Environment

- **Tool:** Wireshark
- **Operating system:** [Windows / Kali Linux]
- **Network interface:** [Wi-Fi / Ethernet / VM interface]
- **Capture type:** [TCP/IPv4 or the actual packet type observed]

## 4. Background: The OSI Model

The OSI model divides network communication into seven conceptual layers.

| Layer | Name | Role |
|---|---|---|
| 7 | Application | Provides network services to applications |
| 6 | Presentation | Describes data representation, encoding, and encryption functions |
| 5 | Session | Describes session establishment and management |
| 4 | Transport | Provides transport between endpoints using protocols such as TCP and UDP |
| 3 | Network | Handles logical addressing and packet routing |
| 2 | Data Link | Handles link-layer delivery and framing |
| 1 | Physical | Transmits bits through electrical, optical, or radio signals |

Not every layer has a separate header in an ordinary network packet. The OSI model is a conceptual framework for understanding communication.

## 5. Procedure

1. Opened Wireshark and selected an active network interface.
2. Started a packet capture.
3. Generated normal network traffic from my own device.
4. Stopped the capture.
5. Applied the display filter `tcp && ip`.
6. Selected a packet containing Ethernet II, IPv4, and TCP, where available.
7. Expanded the protocol sections in the Packet Details pane.
8. Recorded the visible fields and mapped them to the OSI model.
9. Captured screenshots for documentation.

## 6. Packet Observations

Complete the table with values from my actual capture.

| Field | Observed value |
|---|---|
| Frame number | [Enter value] |
| Link-layer protocol | [Enter value] |
| Source MAC address | [Enter value] |
| Destination MAC address | [Enter value] |
| Network-layer protocol | [IPv4 / IPv6] |
| Source IP address | [Enter value] |
| Destination IP address | [Enter value] |
| Transport protocol | [TCP / UDP] |
| Source port | [Enter value] |
| Destination port | [Enter value] |
| TCP flags, if applicable | [Enter value] |
| Application protocol, if identified | [Enter value or unknown] |

## 7. Mapping Packet Fields to the OSI Model

### Layer 2 — Data Link

The Ethernet II section shows link-layer information, including source MAC address, destination MAC address, and EtherType.

These fields help describe delivery over the local network link.

### Layer 3 — Network

The IPv4 section contains source and destination IP addresses, along with fields such as TTL and the protocol identifier.

IP addresses support logical addressing and routing across networks.

### Layer 4 — Transport

The TCP section contains source and destination ports, sequence and acknowledgment numbers, and TCP flags, depending on the selected packet.

TCP supports reliable, ordered delivery through mechanisms including acknowledgments and retransmission.

### Layer 7 — Application

Wireshark may identify protocols such as HTTP, DNS, or TLS when sufficient information is available.

For encrypted traffic, application payloads may not be readable. The presence of TLS does not mean that the encrypted application content is visible.

### Layers 5 and 6 — Session and Presentation

These layers describe functions such as session management, data representation, and encryption.

In ordinary TCP/IP traffic, these functions do not necessarily correspond to separate headers. Their mapping depends on the protocol and the conceptual model being used.

### Layer 1 — Physical

The physical layer represents the transmission of bits over a medium such as copper, fiber, or radio.

Wireshark packet details generally do not display the actual physical signals as a conventional packet header.

## 8. Screenshots

### Packet Overview

![Packet overview](images/packet-overview.png)

This screenshot shows the selected packet in the Wireshark packet list.

### Packet Header Analysis

![Packet header analysis](images/packet-headers.png)

This screenshot shows the expanded protocol sections used for the analysis.

Replace these image references with the actual screenshot files before publishing.

## 9. Key Learnings

- Connected OSI model concepts with real packet observations.
- Identified MAC addresses at the link layer.
- Identified IP addresses at the network layer.
- Identified transport ports and TCP fields at the transport layer.
- Learned that the seven OSI layers do not necessarily correspond to seven distinct packet headers.
- Practiced inspecting protocol information and documenting technical findings.

## 10. Limitations

- The results depend on the selected network interface and captured traffic.
- Encrypted application data may not be readable.
- The visible MAC addresses normally represent the local link, not every router along the complete network path.
- Packet captures do not generally expose physical-layer signals as ordinary protocol headers.
- A single packet cannot demonstrate every function of all seven OSI layers.

## 11. Conclusion

This lab helped me connect the OSI model with practical network traffic analysis. By inspecting a packet in Wireshark, I practiced identifying link-layer, network-layer, and transport-layer fields and understanding how these protocols contribute to communication.

This exercise strengthened my networking fundamentals and provided a foundation for further work in packet analysis and security monitoring.

## 12. Disclaimer

This lab is for educational purposes. Traffic was captured from my own device or an authorized lab environment.
