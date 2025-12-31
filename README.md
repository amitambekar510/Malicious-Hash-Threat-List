# 🔐 Malicious Hash Threat Intelligence Repository  
A curated collection of **malicious file hashes (MD5 / SHA-1 / SHA-256)** that can be used for **blocking, detection and threat hunting** across firewalls, EDR, SIEM, SOAR and other security platforms.

## 📘 Overview  
This repository provides regularly updated lists of malicious file hashes observed across various threat campaigns.  
Security teams can use these lists to:

- Block known malicious files at **firewall / endpoint level**
- Enrich SOC investigations and threat hunting
- Improve detection capabilities by feeding hashes into SIEM/SOAR
- Automate IOC ingestion with EDR or XDR solutions

📢 Update Notice  
• Date: **2025-12-31 14:15 IST** 

• Total Malicious Hashes:

  MD5: **4054** (Each File 3000)
  
  SHA1: **571** (Each File 1000)
  
  SHA256: **80463** (Each File 60000)

## 📁 Repository Structure  
/
├── README.md

├── hashes/

│ ├── md5.txt

│ ├── sha1.txt

│ ├── sha256.txt

## 🧩 Hash Formats Included  

| Hash Type | Usage |

|----------|--------|

| **MD5** | Lightweight integrity checks; some legacy systems |

| **SHA-1** | Better integrity validation; still used by some tools |

| **SHA-256** | Preferred industry standard; most reliable |

|----------|--------|

## 🚀 How to Use  
### **1️⃣ Select the required hash list**
Choose a list under `hashes/` (e.g., `sha256.txt`).

### **2️⃣ Import into your security device**  
Examples:

- **Firewall:** Add hashes to file checksum blocklist
  You can also use RAW link which is as follow:-
  
  MD5:

https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/refs/heads/main/Malicious_md5_hashes_aa.txt

https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/refs/heads/main/malicious_md5_hashes_ab.txt

  SHA1:

https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/refs/heads/main/malicious_SHA1_hashes-aa.txt

  SHA256:

https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/refs/heads/main/malicious_SHA256_hashes_aa.txt

https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/refs/heads/main/malicious_SHA256_hashes_ab.txt
 
- **EDR/XDR:** Import TXT or make it in JSON or CSV as IOC watchlist  
- **SIEM:** Upload to threat intelligence module  
- **SOAR:** Automate enrichment/response playbooks  

### **3️⃣ Monitor for hits**
Any detection or block event should be investigated.

## 🛑 Important Notes  
⚠️ Use responsibly — hash matches indicate a known malicious file but require full investigation.  
⚠️ Hashes cannot detect polymorphic or mutated malware variants.  
⚠️ Verify your organization’s compliance requirements before mass-blocking.  

## 🛠 Contribution Guidelines  
We welcome community contributions!

### **Wish to Contribution then Requirements**
- Only submit **verified malicious hashes**  
- Provide metadata when possible  
- Avoid duplicates  

## 📅 Update Policy  
- Repository updated **weekly** or during major threat events  

✅ Use at Your Own Risk
Anyone using the data should test, verify, and implement it at their own risk, based on their own security policies and environment.

## 👤 Maintainer  
**Amit Ambekar**  
GitHub: *https://www.github.com/amitambekar510*  
Linkedin: *https://www.linkedin.com/in/amitmilindambekar/*
For issues or suggestions, raise an **Issue** in this repository.
