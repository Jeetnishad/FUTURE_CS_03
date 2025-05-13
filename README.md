# 🛡️ Securing Your Own Wi-Fi Networks – Task 3

This project focuses on assessing and improving the security of a personal/home Wi-Fi network. It involves scanning the internal network, identifying connected devices, analyzing traffic using packet captures, and discovering potential vulnerabilities in devices. The goal is to highlight security weaknesses in a typical home setup and recommend practical fixes.

---

## 📁 Project Structure & Contents

### 🔍 Network Scanning & Device Discovery

- `nmap_.png`: Broad Nmap scan of the entire `192.168.1.0/24` subnet to enumerate all active hosts on the local network.
- `nmap_192.168.1.6.png`: Targeted scan of host `192.168.1.6` for open ports and service fingerprinting.

> 📌 Purpose: To identify what devices are online and what services/ports they are exposing to the local network.

### 🔓 Open Ports & Service Enumeration

- `openport_192.168.1.1.png`: Scan of the router/gateway, usually the central point of network control. Reveals services like HTTP and Telnet running.
- `openport_192.168.1.5.png`: Scan of a host (possibly a smart device or PC), showing services like SMB, FTP, or other high-risk ports.

> 🛑 Risk Insight: Ports like Telnet and FTP are inherently insecure. Their presence may allow unauthorized access if not properly secured or disabled.

### 📶 Wireless Traffic Capture & Analysis

- `wifi-security-capture.pcapng`: Captured wireless network traffic using tools like Wireshark or airodump-ng. This includes management and data frames, and may contain handshake data used for WPA2 key cracking.
- `protocol_hierarchy.png`: Wireshark’s protocol breakdown. Helps in understanding the type of traffic present in the network (HTTP, DNS, ARP, etc.).
- `coversations.png`: Conversation statistics to show which IPs are communicating most, revealing potential high-value targets or suspicious communication.

> 📡 Purpose: Understand wireless traffic flow, spot anomalies, and detect unencrypted protocols.

### 🔐 Vulnerability Analysis

- `vuln_192.168.1.5.png`: Vulnerability scan results of host `192.168.1.5`. May include known CVEs, outdated services, or weak configurations.

> 🚨 Key Insight: Known vulnerabilities in IoT or Windows-based devices can be leveraged by attackers to gain access or pivot within the network.

### 🌐 Router Configuration Audit

- `routeradminpage.png`: Screenshot of the router’s web-based admin panel, showing firmware version, exposed services, and login configurations.

> 🔍 Observation: Many routers expose admin panels via HTTP without encryption. Weak/default credentials or outdated firmware are often exploited in real-world attacks.

---

## 🧪 Tools & Technologies Used

| Tool | Purpose |
|------|---------|
| **Nmap** | Host discovery, port scanning, service detection |
| **Wireshark** | Deep packet inspection and protocol analysis |
| **Aircrack-ng / Airodump-ng** | Wi-Fi traffic capture (if used) |
| **[Vulnerability Scanner]** | Assessment of host vulnerabilities (e.g., Nessus, OpenVAS, Nikto) |
| **Web Browser** | Router interface inspection and documentation |

---

## 🧠 Key Security Observations

- ❌ **Telnet exposed** on the router: Outdated and insecure protocol that should be disabled.
- ❌ **Unencrypted HTTP access** to router admin panel: Makes it susceptible to MITM attacks.
- ⚠️ **Potentially exploitable vulnerabilities** found on host `192.168.1.5`.
- 🧷 **Wi-Fi handshake captured** – could be used to brute-force the WPA2 passphrase.
- 🔁 **Insecure traffic protocols** (e.g., ARP flooding, DNS) detected within the network.

---

## ✅ Recommendations

- 🔐 **Disable Telnet** and other insecure services on all networked devices.
- 🧱 **Use strong Wi-Fi encryption** (WPA3 if supported) and a secure passphrase.
- ⚙️ **Update router firmware** to patch known vulnerabilities.
- 🔍 **Regularly audit connected devices** to identify unauthorized access.
- 🧠 **Educate users** on phishing, credential reuse, and device hardening.

---

## ⚠️ Disclaimer

> This project was conducted in a **controlled and authorized environment** for educational and personal security assessment purposes only. All network scans and traffic captures were done on my own Wi-Fi network. **Do not replicate this activity on networks you do not own or have permission to test**—it is illegal and unethical.

---

## 👨‍💻 Author

**Jeet Nishad**  
📧 Email: `jeetnishad12@gmail.com`  
🔐 Passionate about ethical hacking, cybersecurity, and network defense.

---

## 📚 License

This repository is licensed under the [MIT License](https://choosealicense.com/licenses/mit/). You are free to use this material for learning, research, or academic purposes.



