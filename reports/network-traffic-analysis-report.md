\# Network Traffic Analysis with Wireshark



\## 1. Project Overview



This project demonstrates practical network traffic analysis using Wireshark in a controlled virtual laboratory. The investigation focused on ICMP connectivity, TCP connection establishment, HTTP communication, and DNS name resolution.



The project also included troubleshooting network connectivity issues involving VirtualBox NAT, host-only networking, and Linux NetworkManager.



\## 2. Lab Environment



| Component | Configuration |

|---|---|

| Virtualization | Oracle VirtualBox |

| Analysis workstation | Kali Linux |

| Target system | Metasploitable 2 |

| Packet analyzer | Wireshark 4.0.7 |

| Kali NAT interface | eth0 — 10.0.2.15 |

| Kali host-only interface | eth1 — 192.168.56.102 |

| Metasploitable host-only IP | 192.168.56.103 |

| Host-only network | 192.168.56.0/24 |



\## 3. Investigation 1 — ICMP Traffic Analysis



\*\*Objective:\*\* Examine ICMP echo requests and replies to verify connectivity between Kali Linux and Metasploitable.



\*\*Procedure:\*\*



1\. Started a Wireshark capture on Kali's host-only interface.

2\. Generated ICMP traffic using the Linux `ping` command.

3\. Applied the `icmp` display filter.

4\. Examined the request and response packets.



\*\*Findings:\*\*



\- Four ICMP echo requests were captured.

\- Four corresponding ICMP echo replies were captured.

\- Echo requests used ICMP Type 8, Code 0.

\- Request and reply packets demonstrated successful host-to-host communication.



\*\*Evidence:\*\*



\- `01-icmp-request-reply-analysis.png`

\- `01-icmp-connectivity-analysis.pcapng`

\- `01-icmp-filtered-capture.pcapng`



\## 4. Investigation 2 — TCP Three-Way Handshake



\*\*Objective:\*\* Analyze how TCP establishes a connection and observe HTTP communication between two virtual machines.



\*\*Procedure:\*\*



1\. Captured traffic on Kali's host-only interface.

2\. Sent an HTTP HEAD request to the Metasploitable web server.

3\. Examined TCP connection establishment in Wireshark.

4\. Identified the HTTP request, server response, and connection termination.



\*\*Findings:\*\*



\- Kali initiated a TCP connection to destination port 80.

\- The connection followed the SYN → SYN-ACK → ACK sequence.

\- The initial SYN packet had

