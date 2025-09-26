# Task 4 — Setup and Use a Firewall (Windows)

**Author:** Likhith Bharadwaj Reddy  

---

##  Objective
Configure the Windows Defender Firewall to **block Telnet (port 23)** while ensuring that **SSH (port 22)** remains allowed.  
The task involves creating, verifying, testing, and finally removing firewall rules using PowerShell.

---

##  Deliverables
- `commands/firewall-commands-windows.txt` — all PowerShell commands used  
- `exports/firewall-config.wfw` — exported Windows firewall configuration (optional)  
- `README.md` — documentation of the process (includes report section)  

---

##  Steps Performed

1. **Opened PowerShell as Administrator**  
   - Start → Search → `PowerShell` → Right-click → **Run as Administrator**  

2. **Allowed SSH (port 22)**  
   Ensured remote access was not blocked:  
   ```powershell
   New-NetFirewallRule -DisplayName "Allow SSH" -Direction Inbound -LocalPort 22 -Protocol TCP -Action Allow
