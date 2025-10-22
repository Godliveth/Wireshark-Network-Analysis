.## Wireshark Network Traffic Analysis Report
---

## 📘 Overview

This report documents my 5-day hands-on exploration of **Wireshark** as part of my SOC Analyst training. The goal was to understand how different types of network traffic (ICMP, TCP, UDP, DNS, and HTTP) behave and how to interpret them within packet captures.

Each section below includes a short explanation and a link to the actual packet capture screenshot stored in the `/images` folder.

**System Used:** Kali Linux Terminal (Single VM setup due to resource constraints)

---

## 🔹 ICMP Traffic Analysis

* Observed ICMP Echo Requests and Replies during a simple ping operation.
* Learned how ICMP works at the network layer for testing reachability.
* Key takeaway: The **Request (Type 8)** and **Reply (Type 0)** messages confirm bidirectional communication.

[View Screenshot](./images/Icmp_test.png) 

---

## 🔹 TCP Handshake Analysis

* Captured the **three-way handshake**: SYN → SYN/ACK → ACK.
* Understood how the client initiates the session and the server responds.
* Learned how to identify TCP flags in Wireshark for connection establishment and teardown.

[View Screenshot](./images/tcp.png)
[View Screenshot](./images/TCP_flags.png)

---

## 🔹 Closed Port & RST Flag Analysis

* Simulated traffic to closed ports to observe **TCP RST (Reset)** behavior.
* Understood that RST indicates the connection request was refused.
* Learned how SOC analysts use this to detect scanning or probing attempts.

[View Screenshot](./images/Failed_and_Refused_TCP_Flags.png)
[View Screenshot](./images/Tcp_Flag_RST.png)

---

## 🔹 UDP Traffic Analysis

* Sent UDP packets to observe connectionless communication.
* Learned that UDP lacks a handshake and reliability mechanism.
* Compared UDP behavior against TCP for SOC monitoring.

[View Screenshot](./images/udp.png)

---

## 🔹 DNS Query Observation

* Captured DNS lookups to see how name resolution works (Query and Response).
* Observed packet fields: Query Name, Response IP, and Query Type (A record).
* Understood how DNS can be used or abused in tunneling or exfiltration.

[View Screenshot](./images/dns.png)

---

## 🔹 HTTP Traffic Analysis

* Analyzed HTTP GET requests made from a browser.
* Examined **HTTP headers**, including Host, User-Agent, and Methods.
* Understood how analysts trace suspicious HTTP sessions in logs.

[View Screenshot](./images/http.png)
[View Screenshot](./images/get_http.png)
[View Screenshot](./images/User_Agent.png)

---

## 🔹 ARP Analysis

* Observed ARP Requests and Replies to understand MAC address resolution.
* Learned how ARP poisoning attacks can be detected by irregular ARP broadcasts.

[View Screenshot](./images/ARP.png)

---

## 🔹 Network Scanning with Nmap

* Used `sudo nmap` within Kali Linux to simulate network discovery.
* Observed how SYN packets appear in Wireshark and correlate to open ports.
* Connected this to SOC detection use cases like port scan detection.

[View Screenshot](./images/sudo_nmap.png)

---

## 🧩 Summary of Key Learnings

| Protocol | Key Insight                      | SOC Relevance                            |
| -------- | -------------------------------- | ---------------------------------------- |
| ICMP     | Request & Reply for reachability | Detect ping sweeps                       |
| TCP      | Connection setup & teardown      | Connection analysis, threat detection    |
| UDP      | No handshake, connectionless     | Detection of exfiltration via UDP        |
| DNS      | Domain resolution                | Identify suspicious domains or tunneling |
| HTTP     | Application layer communication  | Detect abnormal web traffic              |
| ARP      | MAC-IP mapping                   | Identify spoofing or poisoning attacks   |

---

## 🛠️ Tools Used

* **Wireshark** — Packet capture and protocol analysis.
* **Kali Linux Terminal** — Command-line network testing (ping, nmap).
* **VirtualBox** — Single VM environment setup.

---

## 🧠 Reflection

This exercise strengthened my foundational skills in **network traffic analysis**. I learned how to recognize normal versus abnormal packet behavior, interpret protocol-level data, and connect these patterns to potential SOC detection use cases.

> This hands-on project marks a key milestone in my SOC Analyst learning journey.

---

📸 All screenshots are stored in the `/images` folder.
➡️ To view them directly, click on any **[View Screenshot]** link above.


**Author:** Godliveth Madu
