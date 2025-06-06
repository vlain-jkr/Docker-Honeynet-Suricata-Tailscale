# Docker-Honeynet-Suricata-Tailscale

### **[Docker Honeynet + Suricata + Tailscale](https://github.com/vlain-jkr/docker-honeynet-lab)**

> "You see, in their last moments... people show you who they really are. So let's build a lab that *really* tests them."

This is not just a project — it's a trap with style.  
A **honeynet fortress**, where attackers think they're hunting, but they're the ones being watched.  
Welcome to the **Docker Honeynet Lab**, where every packet tells a story:

- 🎯 Honeypots to lure and trap  
- 🔍 Suricata IDS to detect and alert  
- 🔒 nftables to slice traffic with surgical segmentation  
- 🌐 Tailscale for remote, encrypted villainy monitoring  

---

## 🛠️ What This Project Delivers  

- A **multi-container vulnerable environment** (DVWA, Juice Shop, WebGoat)  
- **nftables rules** to simulate realistic network barriers and blind spots  
- **Suricata IDS** for real-time detection, logging, and packet analysis  
- Remote attacker simulation through **Tailscale VPN**  
- A safe sandbox to practice intrusion detection, alert tuning, and log correlation  

---

## ⚙️ Core Lab Stack  

| Component        | Role                                        |
|------------------|---------------------------------------------|
| 🐳 Docker         | Containerizes vulnerable services           |
| 🧱 nftables       | Enforces network segmentation               |
| 🕵️ Suricata       | Monitors traffic and detects threats        |
| 🔐 Tailscale      | Secures remote access for testing safely    |

---

## 🔥 Sample nftables Rule (Segmentation)  

```bash
# Create base table and chain
nft add table inet filter
nft add chain inet filter forward { type filter hook forward priority 0 ; policy drop ; }

# Optional: explicitly deny traffic between subnets (if you want verbose clarity)
nft add rule inet filter forward ip saddr 10.5.0.0/24 ip daddr 10.6.0.0/24 drop
```

⚠️ **Note**: The last line may be **redundant** if your chain's policy is already `drop`, and you haven’t allowed anything else. Keep it for clarity or logging triggers.

---

## 🔐 Secure Access via Tailscale  

Using Tailscale, you can safely VPN into the honeynet environment, allowing remote monitoring or offensive simulation without exposing the services publicly. Bonus: works seamlessly even behind NAT.

---

## 🧪 Simulated Attacks  

Trigger alerts and test detections using tools like:  
- 🔍 `nmap` — port scans  
- 🔐 `hydra` — brute force attacks  
- 🕳️ `netcat` — simulate backdoors  
- ☠️ `metasploit` — full payload deployment  

---

## 📊 Logs & Detection  

- Use `Suricata` with **custom rule tuning** to catch and classify malicious behavior  
- Export logs for **log correlation** with ELK, Splunk, or a custom parser  
- Bonus: Add **MITRE ATT&CK tags** to classify events  

---

## 🎯 Skills You’ll Practice  

- Docker containerization  
- Honeypot deployment  
- Network segmentation with nftables  
- VPN access and secure tunneling  
- Intrusion detection and log analysis  
- SOC analyst and red team tactics

---

## 🤡 Final Thoughts  

This isn’t just a honeynet — it’s your own little underworld simulation.  
Let attackers play in your arena. You’ve already rigged the rules, set the traps, and pressed record.

---

## 👤 About Me  

I'm Gunveer Singh (aka `vlain-jkr`) — making packets bleed, trapping bad actors, and laughing while my firewall silently drops them.  
Want chaos with control? Fork this lab. Clone your villain lair. Let’s get loud with logs.

---
