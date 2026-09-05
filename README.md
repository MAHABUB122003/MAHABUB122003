<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=700&size=42&duration=2800&pause=600&color=00D4FF&center=true&vCenter=true&width=900&lines=WordPress+Malware+Removal;Complete+Incident+Response+Playbook;Detect.+-+Analyze.+-+Eradicate.+-+Harden." alt="Typing SVG" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Audience-Web%20Security%20Analysts-00D4FF?style=for-the-badge&logo=security&logoColor=white" />
  <img src="https://img.shields.io/badge/License-For%20Educational%20Use-red?style=for-the-badge&logo=license&logoColor=white" />
  <img src="https://img.shields.io/badge/Author-MD%20MAHABUBUR%20RAHMAN-blue?style=for-the-badge&logo=github&logoColor=white" />
</p>

---

## 📌 Overview

A **complete, battle-tested toolkit** for detecting, analyzing, and eradicating WordPress malware infections. This repository documents real-world malware patterns, web shell behaviors, defense mechanisms, and hardening playbooks used by security professionals.

```
WordPress-Malware-Removal/
│
├── BackdoorPHP/                        ← PHP backdoor / web shell analysis
│   ├── (analyzed backdoor samples)
│   └── (behavioral analysis)
│
├── DEFENCE/                            ← General defense playbooks
│   └── (defensive techniques)
│
├── DEFENCEin/                          ← In-depth defense hardening
│   └── (advanced countermeasures)
│
├── Protect .htaccess/                  ← Apache .htaccess hardening
│   └── (blocking rules & patterns)
│
├── WordPress Security Plugin Stack/    ← Recommended plugin stack
│   └── (curated security plugin list)
│
├── wordpress/                          ← Core WordPress hardening
│   └── (wp-config, permissions, cleanup)
│
└── README.md
```

---

## 🔍 What's Inside

### 1️⃣ Backdoor Analysis (`BackdoorPHP/`)

Real-world PHP backdoor/web shell samples with:

- **Behavioral analysis** — how each shell operates
- **Indicator patterns** — what to grep for during an infection
- **Detection signatures** — YARA-style patterns and regex
- **Removal steps** — safe eradication procedures

### 2️⃣ Defense Playbooks (`DEFENCE/` & `DEFENCEin/`)

Two-tier defense approach:

| Tier | Focus | Covered |
|---|---|---|
| **DEFENCE** | Immediate response | File scanning, malware identification, safe removal |
| **DEFENCEin** | Advanced hardening | Deep security layers, file integrity, monitoring |

### 3️⃣ .htaccess Protection (`Protect .htaccess/`)

Ready-to-use `.htaccess` hardening rules:

- Block `eval()`, `base64_decode()`, `assert()` in requests
- Prevent direct access to critical files (`wp-config.php`, `.htaccess`)
- Disable PHP execution in upload directories
- Block suspicious user agents and bot traffic
- Firewall-style malware request filtering

### 4️⃣ Security Plugin Stack (`WordPress Security Plugin Stack/`)

Curated, production-recommended plugin stack:

- **WAF & Firewall** — real-time attack blocking
- **Malware Scanner** — scheduled file integrity checks
- **Login Protection** — brute-force & 2FA defense
- **Security Audit Logging** — track admin activity
- **Performance + Cache** — secure caching configuration

### 5️⃣ WordPress Hardening (`wordpress/`)

Core WordPress security configurations:

- `wp-config.php` — **secure configuration** (disable file editing, debug logging, salts)
- **File permissions** — recommended 644/755 matrix
- **User security** — strong password & 2FA enforcement
- **Database hardening** — prefix changes, table security

---

## 🚨 Infection Response Workflow

```
🔴 DETECT          →   🟠 ANALYZE          →   🔵 ERADICATE      →   🟢 HARDEN
   │                       │                      │                      │
   ├─ Suspicious files     ├─ Identify malware    ├─ Clean infected     ├─ Lock down file
   ├─ Unknown timestamps   ├─ Trace entry point   ├─ Restore clean      ├─ Update everything
   ├─ Unexplained traffic  ├─ Backdoor analysis  ├─ Rebuild htaccess   ├─ Install WAF
   └─ Search engine alerts └─ Find persistence   └─ Change secrets     └─ Enable monitoring
```

---

## 🛡️ Common WordPress Malware Patterns

| Pattern | Evidence | Indicator |
|---|---|---|
| **Hidden Backdoors** | Obfuscated PHP in themes/plugins | `eval(gzinflate(`, `base64_decode(` |
| **SEO Spam Injection** | Hidden spam links in `index.php` | Encoded strings + href injections |
| **Web Shells** | Single-file RCE scripts | `c99shell`, `b374k`, custom shells |
| **Redirect Malware** | Visitors redirected to malicious sites | JS-based `window.location` payloads |
| **Crypto Miners** | Server CPU spikes | Injected miner JavaScript |
| **WooCommerce Skimmers** | Stolen payment data | `jQuery` keylogger / form hijacks |

---

## ⚡ Quick Start

### 1. Scan for Suspicious Files

```bash
# Find recently modified PHP files
find /var/www -name "*.php" -mtime -7

# Find obfuscated code
grep -r "eval(\s*base64_decode" /var/www/wp-content/

# Check for hidden files
find /var/www -name ".*.php" -type f
```

### 2. Check .htaccess Integrity

```bash
# Look for injected redirect rules
grep -n "RewriteRule\|Order deny" .htaccess
```

### 3. Verify Against Fresh Core

```bash
# Compare checksums against fresh WP core
diff -r /path/to/wp-load.php /path/to/clean/wp-load.php
```

### 4. Apply Hardening

Deploy the **`.htaccess` rules** and **security plugin stack** from this repository to prevent reinfection.

---

## 🔒 Defense-in-Depth Strategy

```
WordPress → Firewall (WAF) → .htaccess Rules → Plugin Hardening
    → Core Updates → File Integrity Monitoring → Log Analysis
        → Database Security → Backup & Recovery
```

---

## 📝 License & Disclaimer

> This toolkit is provided for **educational and defensive security purposes only**. The techniques documented here are intended for **hardening your own WordPress installations** or responding to infections **on systems you own or are authorized to manage**. The author assumes no liability for misuse.

---

## 👨‍💻 Author

**MD MAHABUBUR RAHMAN**
Full-Stack Developer & Cybersecurity Specialist

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/MAHABUB122003)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/md-mahabubur-rahman-mahabub-41674b33a)

---

<p align="center">
  <img src="https://img.shields.io/badge/Defend_WordPress_against_malware-00D4FF?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Stay_Secure_Stay_Hardened-green?style=for-the-badge" />
</p>
