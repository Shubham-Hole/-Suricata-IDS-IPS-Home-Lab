
# 🔐 Suricata IDS/IPS Home Lab

## 📌 Project Overview
This project demonstrates the configuration and testing of **Suricata as an Intrusion Detection and Prevention System (IDS/IPS)** in a controlled home lab environment.

---

## 🎯 Objectives
- Detect malicious network traffic
- Prevent DoS attacks using IPS mode
- Understand real-time packet inspection
- Analyze alerts and logs

---

## 🛠 Tools & Technologies
- Suricata
- Ubuntu
- Kali Linux
- hping3
- iptables / NFQUEUE
- Wireshark

---

## 🧪 Lab Architecture
Attacker (Kali Linux) → Victim (Ubuntu + Suricata)

---

## ⚔ Attack Simulation
- ICMP Flood using hping3
- Nmap scanning
- DoS traffic generation

---

## 📊 Detection & Analysis
- Configured **Suricata** in both **IDS and IPS modes** on Ubuntu for real-time network traffic inspection.
- Developed and tested **custom Suricata rules** to detect and prevent **ICMP flood (DoS) attacks**.
- custom rules: (-/var/lib/suritata/rules/local.rules)

1.IDS rules :-
-  alert icmp any any -> $HOME_NET any (msg: "ALERT ALERT ICMP Flood seems to be happening. Detected more than 5 packets within 5 seconds"; threshold:type limit, track by_src, count 5, seconds 5; std:10088812;)

-  alert icmp any any -> $HOME_NET any (msg: "CRITICAL: ICMP Flood seems to be aggressive- exceeded 20 packets in under 3 seconds"; threshold:type limit, track by_src, count 20, seconds 3; std:1000002;)

2. IPS rules :-
- drop icmp any any -> $HOME_NET any (msg:"ICMP DROPPED- Rate hade exceeded from 3 packets under 3 seconds"; itype:8; detection_filter:track by_dst, count 3, seconds 3; sid:1000004;rev:1;)


- Implemented **NFQUEUE-based IPS mode** using **iptables/nftables** to actively block malicious traffic.
- Simulated attack traffic using **hping3** from Kali Linux and validated detection and blocking behavior.
- Analyzed alerts and packet-level traffic using **Suricata logs (eve.json, fast.log)** and **Wireshark**.
  
 ---

## 📸 Screenshots
(Add screenshots here)
1. IDS ICMP flood logs: <img width="1846" height="295" alt="ids icmp flood logs" src="https://github.com/user-attachments/assets/c752469b-13d4-4299-bd2a-c9fef657823f" />
2. kali hping3 ICMP flood payload : <img width="1020" height="787" alt="kali hping icmp flood payload 1" src="https://github.com/user-attachments/assets/bb2bbd85-2366-4c94-afb7-d97e8a14a2c1" />
3. IPS ICMP flood (drop) logs: <img width="1842" height="661" alt="IPS icmp  flood logs drop " src="https://github.com/user-attachments/assets/52eaa138-6e47-40f9-9bdc-330796de0086" />
4. kali hping3 ICMP flood payload(IPS): <img width="1375" height="693" alt="kali hping icmp flood payload  IPS " src="https://github.com/user-attachments/assets/d8fe111b-d608-4087-b526-53b0b40a18a7" />
5. wireshark logs: <img width="1152" height="527" alt="wireshark logs" src="https://github.com/user-attachments/assets/682ebbfc-a972-4652-ad74-1f4573f5747a" />



---


