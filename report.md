# Report — How Windows Firewall Filters Traffic
**Author:** Likhith Bharadwaj Reddy 

##  Introduction
The Windows Defender Firewall is a built-in, stateful firewall that monitors and controls network traffic.  
It applies rules to decide whether specific inbound or outbound connections are allowed or blocked.  
For this task, the goal was to **allow SSH (port 22)** and **block Telnet (port 23)**.

---

##  How Windows Firewall Filters Traffic
1. **Rule Creation**  
   - Rules define which traffic is permitted or denied.  
   - Rules can be based on:  
     - **Port numbers** (e.g., 22 for SSH, 23 for Telnet)  
     - **Protocol** (TCP, UDP)  
     - **Direction** (Inbound or Outbound)  
     - **Program or service**  

2. **Inbound vs Outbound**  
   - **Inbound rules**: Filter traffic coming into the system from the network.  
   - **Outbound rules**: Filter traffic leaving the system.  
   - In this task, inbound rules were created to allow or block specific ports.  

3. **Stateful Filtering**  
   - Windows Firewall tracks the state of active connections.  
   - If an inbound rule allows traffic, return traffic is automatically allowed without requiring another rule.  

---

##  Example Configuration (PowerShell)
- **Allow SSH (22)** to ensure secure remote access:  
  ```powershell
  New-NetFirewallRule -DisplayName "Allow SSH" -Direction Inbound -LocalPort 22 -Protocol TCP -Action Allow
