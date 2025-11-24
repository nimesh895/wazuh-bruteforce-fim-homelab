# wazuh-bruteforce-fim-homelab
SOC Analyst Homelab — Wazuh SIEM: Brute-Force RDP Attack Detection + Custom Rules + FIM

# Wazuh SOC Homelab — Brute-Force Attack + Custom Rules + FIM

![Brute Force Attack Simulation](run%20bruteforce%20attack.png)

**Real-world SOC Analyst project**: Simulated RDP brute-force attack from Kali → Windows 11 → Detected & alerted using **custom Wazuh correlation rules** + File Integrity Monitoring (FIM).

### Lab Environment
| Machine        | Role                          | OS            |
|----------------|-------------------------------|---------------|
| Ubuntu Server  | Wazuh Manager + Dashboard    | Ubuntu 22.04  |
| Windows 11     | Victim (RDP enabled)          | Windows 11    |
| Kali Linux     | Attacker (Hydra brute-force)  | Kali 2025     |

### Achievements
- Successfully collected Windows Event ID 4625 (failed logins)
- Simulated real RDP brute-force attack using **Hydra**
- Wrote and deployed **custom detection rule** in `local_rules.xml`
- Triggered high-severity alerts in Wazuh dashboard
- Configured **File Integrity Monitoring (FIM)** on critical Windows system files
- Detected unauthorized modification of `C:\Windows\System32\drivers\etc\hosts`

### Attack & Detection Flow
1. **Enabled RDP + allowed through firewall**  
   ![Firewall Rule](make%20sure%20firewall%20allow%20rdp.png)

2. **Created custom password list**  
   ![Wordlist](unzip%20and%20check%20wordlist%20for%20hydra.png)

3. **Launched Hydra brute-force attack**  
   ![Hydra Running](run%20bruteforce%20attack.png)  
   ![3 Failed Attempts](found%203%20failed%20login%20attempts.png)

4. **Custom rule triggered in Wazuh**  
   ![Custom Rule Alert](created%20custom%20rules%20for%20one%20failed%20login%20attempts%20and%20b.png)

5. **FIM detected file change**  
   ![FIM Alert](capture%20the%20failed%20login%20on%20wazuh%20dashboard.png)

### Skills Demonstrated (Tier-1 SOC Analyst Level)
- Log collection & parsing (Event ID 4625)
- Brute-force attack simulation with Hydra
- Writing custom SIEM correlation rules
- File Integrity Monitoring configuration
- Incident detection & alerting workflow
- Real-world threat hunting basics

### Tools Used
- Wazuh (open-source SIEM/XDR)
- Hydra (THC)
- Kali Linux
- Windows 11 + RDP
- VirtualBox

### Next Steps
- Add active response (auto-block attacker IP)
- Integrate with TheHive for incident response
- MITRE ATT&CK mapping of alerts
- Sysmon + custom Wazuh decoders

---
**Original Documentation**: [brute force simulation homelab.pdf](brute%20force%20simulation%20homelab.pdf)

**Author**: Nimesh Akalanka Peiris  
**LinkedIn**: [linkedin.com/in/nimesh23](https://www.linkedin.com/in/nimesh23)  
**Year**: 2025

---
**This project is 100% portfolio-ready — perfect for SOC Analyst, Blue Team, or Security Operations roles**
