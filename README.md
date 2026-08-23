<div align="center">

```
███╗   ███╗██╗███╗   ██╗██╗███████╗████████╗ █████╗ ██████╗  ██████╗ ██████╗ ██████╗ ██╗   ██╗
████╗ ████║██║████╗  ██║██║██╔════╝╚══██╔══╝██╔══██╗██╔══██╗██╔═══██╗██╔══██╗██══██╗╚██╗ ██╔╝
██╔████╔██║██║██╔██╗ ██║██║███████╗   ██║   ███████║██████╔╝██║   ██║██████╔╝██████╔╝ ╚████╔╝
██║╚██╔╝██║██║██║╚██╗██║██║╚════██║   ██║   ██╔══██║██╔══██╗██║   ██║██══██╗██══██╗  ╚██╔╝
██║ ╚═╝ ██║██║██║ ╚████║██║███████║   ██║   ██║  ██║██║  ██║╚██████╔╝██║  ██║██║  ██║   ██║
╚═╝     ╚═╝╚═╝╚═╝  ╚═══╝╚═╝╚══════╝   ╚═╝   ╚═╝  ╚═╝╚═════╝ ╚═════╝ ╚═════╝ ╚═════╝   ╚═╝
```

# 🟣 Malicious Hash Threat Intelligence Feed
### Curated collection of malicious file hashes (MD5 / SHA-1 / SHA-256) for endpoint defense

![Feed Status](https://img.shields.io/badge/Feed-ACTIVE-9b59b6?style=for-the-badge)
![SHA256](https://img.shields.io/badge/SHA256-80,644+-9b59b6?style=for-the-badge)
![MD5](https://img.shields.io/badge/MD5-4,134+-9b59b6?style=for-the-badge)
![SHA1](https://img.shields.io/badge/SHA1-627+-9b59b6?style=for-the-badge)
![Last Update](https://img.shields.io/github/last-commit/amitambekar510/Malicious-Hash-Threat-List?style=for-the-badge&label=Updated&color=9b59b6)
![Auto-Update](https://img.shields.io/badge/Auto_Update-Every_12h-1abc9c?style=for-the-badge&logo=githubactions)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)
![Build](https://img.shields.io/github/actions/workflow/status/amitambekar510/Malicious-Hash-Threat-List/validate.yml?branch=main&label=Validation&style=for-the-badge)

</div>

---

## 📥 RAW Feed Links (Direct Integration — No Auth Required)

| Hash Type | Part | RAW URL | Count |
|-----------|------|---------|-------|
| **MD5** | Part 1 | `https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/main/Malicious_md5_hashes_aa.txt` | ~3,000 |
| **MD5** | Part 2 | `https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/main/malicious_md5_hashes_ab.txt` | ~1,134 |
| **SHA1** | Part 1 | `https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/main/malicious_SHA1_hashes-aa.txt` | ~627 |
| **SHA256** | Part 1 | `https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/main/malicious_SHA256_hashes_aa.txt` | ~60,000 |
| **SHA256** | Part 2 | `https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/main/malicious_SHA256_hashes_ab.txt` | ~60,000 |
| **SHA256** | Part 3 | `https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/main/malicious_SHA256_hashes_ac.txt` | ~644 |

> 💡 **New partition files** are created automatically when a partition reaches its limit (SHA256: 60K, MD5: 3K, SHA1: 1K). Update your tool configs to include all part URLs.

---

## 📊 Feed Statistics

| Hash Type | Total | Partitions | Max/Partition | Validation |
|-----------|-------|------------|---------------|------------|
| **MD5** | 4,134 | 2 | 3,000 | VirusTotal (≥3), MalwareBazaar |
| **SHA1** | 627 | 1 | 1,000 | VirusTotal (≥3), MalwareBazaar |
| **SHA256** | 80,644 | 3 | 60,000 | VirusTotal (≥3), MalwareBazaar |
| **TOTAL** | **85,405** | **6** | — | — |

### Hash Format Standards

| Type | Length | Charset | Example |
|------|--------|---------|---------|
| MD5 | 32 | lowercase hex | `d41d8cd98f00b204e9800998ecf8427e` |
| SHA1 | 40 | lowercase hex | `da39a3ee5e6b4b0d3255bfef95601890afd80709` |
| SHA256 | 64 | lowercase hex | `e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855` |

---

## 🔄 Automated Update Pipeline

```mermaid
flowchart TB
    subgraph Sources["🔍 Threat Intelligence Sources"]
        S1[MalwareBazaar Recent<br/>(Latest 100 samples via API)]
        S2[MalwareBazaar by Type<br/>(PE executables, DLLs, scripts)]
    end

    Collect["🤖 Automated Collection<br/>(Every 12h via GitHub Actions)"]
    Validate["✅ Multi-Source Validation<br/>VT ≥3 detections · MalwareBazaar confirmed"]
    Dedup["🚫 Zero-Duplicate Guarantee<br/>Bloom Filter + Git History + Cross-Type"]
    Repos["📦 Partitioned by Type<br/>SHA256: 60K/file · MD5: 3K/file · SHA1: 1K/file"]
    Deploy["🚀 Direct Tool Integration<br/>CrowdStrike · SentinelOne · FortiGate · Splunk · MDE · ELK · MISP"]

    Sources --> Collect --> Validate --> Dedup --> Repos --> Deploy

    classDef source fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px,color:#4a148c;
    classDef process fill:#e3f2fd,stroke:#1565c0,stroke-width:2px,color:#0d47a1;
    classDef output fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px,color:#1b5e20;
    classDef final fill:#fff3e0,stroke:#ef6c00,stroke-width:2px,color:#e65100;

    class S1,S2 source;
    class Collect,Validate,Dedup process;
    class Repos output;
    class Deploy final;
```

---

## 🛠️ Security Tool Integration Guides

<div align="center">

### Quick Reference — All Platforms Support 12h Refresh

| Platform | Hash Types | Integration Type | Config Guide |
|----------|------------|------------------|--------------|
| **CrowdStrike Falcon** | SHA256, MD5, SHA1 | Custom IOC Management | [📖 Guide](https://github.com/amitambekar510/Malicious-Hash-Threat-List/blob/main/docs/integration-crowdstrike.md) |
| **SentinelOne** | SHA256, MD5, SHA1 | Bulk IOC Import (API/CSV) | [📖 Guide](https://github.com/amitambekar510/Malicious-Hash-Threat-List/blob/main/docs/integration-sentinelone.md) |
| **FortiGate / FortiSandbox** | SHA256 | External Connectors → Malware Hash | [📖 Guide](https://github.com/amitambekar510/Malicious-Hash-Threat-List/blob/main/docs/integration-fortigate.md) |
| **Splunk ES** | SHA256, MD5, SHA1 | Intelligence Downloads (file_intel) | [📖 Guide](https://github.com/amitambekar510/Malicious-Hash-Threat-List/blob/main/docs/integration-splunk.md) |
| **Microsoft Defender for Endpoint** | SHA256, MD5, SHA1 | Indicators → File Hash | [📖 Guide](https://github.com/amitambekar510/Malicious-Hash-Threat-List/blob/main/docs/integration-mde.md) |
| **Palo Alto WildFire** | SHA256 | File Blocking Profile / WildFire API | [📖 Guide](https://github.com/amitambekar510/Malicious-Hash-Threat-List/blob/main/docs/integration-paloalto.md) |
| **ELK Stack** | SHA256, MD5, SHA1 | Logstash http_poller (auto-detect type) | [📄 Pipeline](https://github.com/amitambekar510/Malicious-Hash-Threat-List/blob/main/elk-pipeline.conf) |
| **MISP** | SHA256, MD5, SHA1 | Freetext Feed Import (by type) | [🐍 Script](https://github.com/amitambekar510/Malicious-Hash-Threat-List/blob/main/misp_import.py) |

</div>

### 🟢 CrowdStrike Falcon

```
Threat Intelligence → Indicators → Custom IOC Management
→ Upload IOCs → Bulk Import (CSV/TXT)
→ Map: type: SHA256 / MD5 / SHA1
→ Action: Block (confirmed malicious) | Detect (monitoring)
```

**CSV Format:**
```csv
type,value,source,description,method
SHA256,e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855,GitHub-TI,Malicious File Hash,BLOCK
MD5,d41d8cd98f00b204e9800998ecf8427e,GitHub-TI,Malicious File Hash,BLOCK
SHA1,da39a3ee5e6b4b0d3255bfef95601890afd80709,GitHub-TI,Malicious File Hash,BLOCK
```

---

### 🟣 SentinelOne EDR/XDR

**Python Bulk Import:**
```python
import requests

S1_URL   = "https://<your-instance>.sentinelone.net"
S1_TOKEN = "<your-api-token>"
FEED_URL = "https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/main/malicious_SHA256_hashes_aa.txt"

hashes = requests.get(FEED_URL).text.splitlines()
hashes = [h for h in hashes if h and not h.startswith('#')]

indicators = [
  {
    "type": "SHA256",
    "value": hash_val,
    "source": "GitHub-TI",
    "description": "Malicious file hash — GitHub Threat Intelligence Feed",
    "method": "BLOCK"
  }
  for hash_val in hashes
]

headers = {"Authorization": f"ApiToken {S1_TOKEN}", "Content-Type": "application/json"}
response = requests.post(
  f"{S1_URL}/web/api/v2.1/threat-intelligence/iocs",
  headers=headers, json={"data": indicators}
)
print(f"Imported {len(indicators)} SHA256 hashes — Status: {response.status_code}")
```

**Manual CSV Import (all hash types):**
```csv
type,value,source,description,method
SHA256,<hash>,GitHub-TI,Malicious File Hash,BLOCK
MD5,<hash>,GitHub-TI,Malicious File Hash,BLOCK
SHA1,<hash>,GitHub-TI,Malicious File Hash,BLOCK
```

---

### 📊 ELK Stack (Logstash + Kibana)

Save as `/etc/logstash/conf.d/github-ti-hash-feed.conf`:

```ruby
input {
  http_poller {
    urls => {
      github_sha256_p1 => "https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/main/malicious_SHA256_hashes_aa.txt"
      github_sha256_p2 => "https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/main/malicious_SHA256_hashes_ab.txt"
      github_sha256_p3 => "https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/main/malicious_SHA256_hashes_ac.txt"
      github_md5_p1    => "https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/main/Malicious_md5_hashes_aa.txt"
      github_sha1_p1   => "https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/main/malicious_SHA1_hashes-aa.txt"
    }
    request_timeout => 120
    schedule        => { "every" => "12h" }
    codec           => "line"
    add_field       => { "indicator_kind" => "hash" }
  }
}

filter {
  if [message] =~ /^\s*#/ or [message] =~ /^\s*$/ { drop { } }
  mutate { strip => ["message"] }
  
  # Determine hash type by length
  ruby {
    code => '
      hash = event.get("message")
      if hash.length == 32
        event.set("[threat][indicator][file][hash][md5]", hash)
        event.set("[threat][indicator][type]", "md5")
      elsif hash.length == 40
        event.set("[threat][indicator][file][hash][sha1]", hash)
        event.set("[threat][indicator][type]", "sha1")
      elsif hash.length == 64
        event.set("[threat][indicator][file][hash][sha256]", hash)
        event.set("[threat][indicator][type]", "sha256")
      end
    '
  }
  
  mutate {
    add_field => {
      "[threat][feed][name]"      => "GitHub-TI-Hashes"
      "[event][category]"         => "threat"
      "[event][type]"             => "indicator"
    }
  }
  ruby { code => 'event.set("[threat][indicator][last_seen]", Time.now.utc.iso8601)' }
  fingerprint { source => ["message"]; target => "[@metadata][doc_id]"; method => "SHA256" }
  mutate { remove_field => ["indicator_kind", "message", "@version"] }
}

output {
  elasticsearch {
    hosts         => ["https://localhost:9200"]
    index         => "github-ti-hash-feed"
    document_id   => "%{[@metadata][doc_id]}"
    action        => "update"
    doc_as_upsert => true
  }
}
```

---

### 🔷 MISP (Open Source TIP)

```bash
# Import SHA256
curl -s "https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/main/malicious_SHA256_hashes_aa.txt" \
  | python3 misp_import.py --type sha256 --feed github-ti --org "Personal TI"

# Import MD5
curl -s "https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/main/Malicious_md5_hashes_aa.txt" \
  | python3 misp_import.py --type md5 --feed github-ti --org "Personal TI"

# Import SHA1
curl -s "https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/main/malicious_SHA1_hashes-aa.txt" \
  | python3 misp_import.py --type sha1 --feed github-ti --org "Personal TI"

# Or use MISP UI:
# Sync → Feeds → Add Feed (per hash type)
#   Format: freetext | Pull: Every 12h
```

---

### 🔴 FortiGate / FortiSandbox

```
Security Fabric → External Connectors → Threat Feed → Create New
  Type: Malware Hash
  URL: https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/main/malicious_SHA256_hashes_aa.txt
  Refresh: Every 12 hours
→ Reference in File Filter / AV Profile → Action: Block
```

---

### 🟠 Splunk SIEM (Enterprise Security)

```
Enterprise Security → Intelligence Downloads → New
  Name:     GitHub-TI-Malicious-Hashes-SHA256
  URL:      https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/main/malicious_SHA256_hashes_aa.txt
  Type:     file_intel
  Interval: 43200 (12 hours)
  Fields:   hash → indicator, hash_type → sha256

# Repeat for MD5 and SHA1 feeds
```

---

### 🔵 Microsoft Defender for Endpoint (MDE)

```
Settings → Endpoints → Indicators → Add indicator
→ Type: File hash (SHA256/MD5/SHA1)
→ Action: Block and remediate
→ Source: Import from CSV (export from RAW feeds)
```

**Bulk Import via API:**
```python
import requests

MDE_TOKEN = "<your-mde-token>"
FEED_URL = "https://raw.githubusercontent.com/amitambekar510/Malicious-Hash-Threat-List/main/malicious_SHA256_hashes_aa.txt"

hashes = requests.get(FEED_URL).text.splitlines()
hashes = [h for h in hashes if h and not h.startswith('#')]

indicators = [
  {
    "indicatorValue": h,
    "indicatorType": "FileSha256",
    "action": "BlockAndRemediate",
    "title": "GitHub-TI Malicious Hash",
    "description": "Malicious file hash from GitHub Threat Intelligence Feed",
    "severity": "High"
  }
  for h in hashes
]

headers = {"Authorization": f"Bearer {MDE_TOKEN}", "Content-Type": "application/json"}
for ind in indicators:
    requests.post("https://api.securitycenter.microsoft.com/api/indicators", headers=headers, json=ind)
```

---

### 🔥 Palo Alto Networks (WildFire / File Blocking)

```yaml
# File Blocking Profile → Custom Block List
# Add SHA256 hashes from RAW feed
# Action: Block | Alert

# Or use WildFire API for automated submission
```

---

## 📁 Repository Structure

```
Malicious-Hash-Threat-List/
├── hashes/
│   ├── md5/
│   │   ├── Malicious_md5_hashes_aa.txt       # Part 1 (3,000)
│   │   └── malicious_md5_hashes_ab.txt       # Part 2 (1,134)
│   ├── sha1/
│   │   └── malicious_SHA1_hashes-aa.txt      # Part 1 (627)
│   └── sha256/
│       ├── malicious_SHA256_hashes_aa.txt    # Part 1 (60,000)
│       ├── malicious_SHA256_hashes_ab.txt    # Part 2 (60,000)
│       └── malicious_SHA256_hashes_ac.txt    # Part 3 (644)
├── README.md                                 # This file
├── CHANGELOG.md                              # Update history
├── CONTRIBUTING.md                           # Contribution guide
├── LICENSE                                   # MIT License
├── elk-pipeline.conf                         # Logstash pipeline config
├── misp_import.py                            # MISP import script
├── sentinelone_import.py                     # SentinelOne import script
└── docs/
    ├── integration-crowdstrike.md
    ├── integration-sentinelone.md
    ├── integration-fortigate.md
    ├── integration-splunk.md
    ├── integration-mde.md
    └── integration-paloalto.md
```

---

## 📝 File Format

```
# ============================================================
# Malicious-Hash-Threat-List — SHA256 Feed | Part 01
# Author        : Amit Ambekar
# Organization  : Personal Threat Intelligence
# Created       : 2024-01-01
# Updated       : 2026-01-15
# Part          : 01 (max 60,000 per file)
# Count         : 80644
# Source        : Multi-source — MalwareBazaar / VirusTotal hunting
# Category      : Malware (Ransomware, Trojan, Miner, Dropper)
# License       : MIT
# Repository    : https://github.com/amitambekar510/Malicious-Hash-Threat-List
# Format        : One SHA256 hash (64 hex chars, lowercase) per line
# ============================================================
e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855
a1b2c3d4e5f6789012345678901234567890abcdef1234567890abcdef123456
...
```

**Format Rules:**
- One hash per line
- Lowercase hexadecimal only
- Exact length: MD5=32, SHA1=40, SHA256=64 chars
- No prefixes, no metadata on same line

---

## 🤝 Contributing

### Report False Positive
[Open an issue](https://github.com/amitambekar510/Malicious-Hash-Threat-List/issues/new?template=false_positive.yml) with:
- Hash value and type
- Reason (legitimate software, false detection, etc.)
- VirusTotal/MalwareBazaar links showing clean status

### Submit New Malicious Hash
[Open an issue](https://github.com/amitambekar510/Malicious-Hash-Threat-List/issues/new?template=ioc_submission.yml) with:
- Hash value (MD5/SHA1/SHA256)
- Malware family/type if known
- Source/evidence (VT link, MalwareBazaar link, sandbox report)

### Request Tool Integration
[Open an issue](https://github.com/amitambekar510/Malicious-Hash-Threat-List/issues/new?template=integration_request.yml) with:
- Tool/platform name
- Configuration steps
- Example config

---

## 📜 License

MIT License — Free for defensive security use.

---

## ⚠️ Disclaimer

> **Hash matches indicate known malicious files but require full investigation.**
> - Hashes cannot detect polymorphic/mutated malware variants
> - Verify your organization's compliance requirements before mass-blocking
> - Legitimate software may share hashes with malware (packers, installers)

---

## 📞 Contact

| | |
|---|---|
| **Maintainer** | Amit Ambekar |
| **GitHub** | [@amitambekar510](https://github.com/amitambekar510) |
| **LinkedIn** | [amitmilindambekar](https://www.linkedin.com/in/amitmilindambekar/) |
| **Portfolio** | [portfolio.thesafehouse.in](https://portfolio.thesafehouse.in) |
| **Collector** | [threat-intel-collector](https://github.com/amitambekar510/threat-intel-collector) |

---

<div align="center">

**⭐ Star this repo if you find it useful!**

*Defending networks, one indicator at a time.*

</div>