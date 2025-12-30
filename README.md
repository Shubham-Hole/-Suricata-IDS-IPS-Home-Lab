
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
- Implemented **NFQUEUE-based IPS mode** using **iptables/nftables** to actively block malicious traffic.
- Simulated attack traffic using **hping3** from Kali Linux and validated detection and blocking behavior.
- Analyzed alerts and packet-level traffic using **Suricata logs (eve.json, fast.log)** and **Wireshark**.
  
 ---

## 📸 Screenshots
(Add screenshots here)

---


