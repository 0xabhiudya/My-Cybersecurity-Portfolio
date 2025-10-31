# Abhiudya's 180-Day Cybersecurity Portfolio

### M.Sc. Cybersecurity | (ISC)² CC | SOC • AppSec • DevSecOps

Welcome to my 6-month challenge to move from advanced theory to job-ready, hands-on practice.  
This repository is the single source of truth for all my projects, labs, and write-ups.

[Connect with me on LinkedIn](https://www.linkedin.com/in/abhiudya-dwivedi)  
[Follow me on X (Twitter)](https://twitter.com/0xabhiudya)

---

## 🚀 My 6-Month Roadmap

Each project lives in its own folder with:
- Full technical write-up (Markdown)
- Code or configs
- Screenshots & architecture diagrams

### 🛡️ Phase 1: SOC & Network Defense (Months 1–3)
- [ ] **Project 01:** SIEM-in-a-Box (Wazuh)
- [ ] **Project 02:** Splunk Dashboard Showcase
- [ ] **Project 03:** Network IDS (Suricata) & Custom Rule
- [ ] **Project 04:** pfSense Firewall Lab

### 💻 Phase 2: AppSec & DevSecOps (Months 4–5)
- [ ] **Project 05:** Manual Pentesting (OWASP Juice Shop)
- [ ] **Project 06:** SAST Integration (SonarQube)
- [ ] **Project 07:** Secure CI/CD Pipeline

### ⚡ Phase 3: The Capstone (Month 6)
- [ ] **Project 08:** The Hybrid Kill Chain (WAF → SIEM → Alert)

---

## 🧩 My Lab Setup

| Component | Tool/OS | Notes |
|------------|----------|-------|
| **Host OS** | Windows 11 / Kali Linux (Dual Boot) | Primary host environment |
| **Virtualization** | VirtualBox | All VMs managed here |
| **Attacker VM** | Kali Linux | Pentesting & red team |
| **Server/SIEM VM** | Ubuntu Server 24.04 LTS | Wazuh, Suricata, Splunk |
| **Victim VM** | Windows Server 2022 | Exploitation & defense testing |

---

## 🧠 About Me

I'm **Abhiudya Dwivedi (0xabhiudya)** — an M.Sc. Cybersecurity graduate building a public portfolio in SOC, AppSec, and DevSecOps.  
I document the wins, the broken configs, and the Zenitsu-level panic moments along the way.

---

⚡ *Follow this repo for daily updates, commits, and chaos.*

**GitHub:** [github.com/0xabhiudya](https://github.com/0xabhiudya)  
**LinkedIn:** [linkedin.com/in/abhiudya-dwivedi](https://www.linkedin.com/in/abhiudya-dwivedi)

## 🧩 Phase 1 – SOC & Network Monitoring
```mermaid
graph TD
    A[Host Machine: Windows 11 / Kali Linux] -->|VirtualBox| B[Ubuntu Server 24.04 LTS – Wazuh SIEM + Suricata IDS]
    A -->|VirtualBox| C[Windows Server 2022 – Victim VM]
    A -->|VirtualBox| D[Kali Linux – Attacker VM]

    subgraph Internal_Network
        B <--> C
        B <--> D
    end

    D -->|Attack Traffic| C
    C -->|Windows Event Logs| B
    B -->|Alerts + Correlations| E[Wazuh / Splunk Dashboard]

    %% Color-coded link styles (index order = link order above)
    linkStyle 0 stroke:#007bff,stroke-width:2px;
    linkStyle 1 stroke:#007bff,stroke-width:2px;
    linkStyle 2 stroke:#007bff,stroke-width:2px;
    linkStyle 3 stroke:#007bff,stroke-width:2px;
    linkStyle 4 stroke:#007bff,stroke-width:2px;
    linkStyle 5 stroke:#ff0000,stroke-width:2px;
    linkStyle 6 stroke:#00cc66,stroke-width:2px;
    linkStyle 7 stroke:#00cc66,stroke-width:2px;
```


## 🧱 Phase 2 – Network Defense with pfSense

```mermaid
graph TD
    A[Host Machine: Windows 11 / Kali Linux] -->|VirtualBox| B[Ubuntu Server 24.04 LTS - Wazuh SIEM + Suricata IDS]
    A -->|VirtualBox| C[Windows Server 2022 - Victim VM]
    A -->|VirtualBox| D[Kali Linux - Attacker VM]
    A -->|VirtualBox| F[pfSense Firewall - Traffic Control + Syslog Export]

    F --> B
    F --> C
    F --> D

    D -->|Attack traffic| F
    F -->|Filtered traffic| C
    C -->|Event logs| F
    F -->|Syslog & IDS alerts| B
    B -->|Correlated events| E[Wazuh / Splunk Dashboard]

    linkStyle 0 stroke:#007bff,stroke-width:2px;
    linkStyle 1 stroke:#007bff,stroke-width:2px;
    linkStyle 2 stroke:#007bff,stroke-width:2px;
    linkStyle 3 stroke:#007bff,stroke-width:2px;
    linkStyle 4 stroke:#007bff,stroke-width:2px;
    linkStyle 5 stroke:#007bff,stroke-width:2px;
    linkStyle 6 stroke:#007bff,stroke-width:2px;
    linkStyle 7 stroke:#ff0000,stroke-width:2px;
    linkStyle 8 stroke:#00cc66,stroke-width:2px;
    linkStyle 9 stroke:#00cc66,stroke-width:2px;

```


## ⚙️ Phase 3 – AppSec + DevSecOps Integration

```mermaid
graph TD
    A[Host Machine: Windows 11 / Kali Linux] -->|VirtualBox| B[Ubuntu Server 24.04 LTS - Wazuh SIEM + Suricata IDS]
    A -->|VirtualBox| F[pfSense Firewall - Traffic Control + Syslog Export]
    A -->|VirtualBox| G[Web Server - OWASP Juice Shop + ModSecurity WAF]
    A -->|Cloud| H[CI/CD Pipeline - GitHub Actions + SonarQube]

    F --> B
    F --> G

    F -->|Filtered traffic| G
    G -->|WAF alerts to SIEM| B
    F -->|Syslog & IDS alerts| B
    H -->|SAST reports & deployments| G
    H -->|DevSecOps alerts| B
    B -->|Correlated events| E[Wazuh / Splunk Dashboard]

    linkStyle 0 stroke:#007bff,stroke-width:2px;
    linkStyle 1 stroke:#007bff,stroke-width:2px;
    linkStyle 2 stroke:#007bff,stroke-width:2px;
    linkStyle 3 stroke:#a020f0,stroke-width:2px;
    linkStyle 4 stroke:#007bff,stroke-width:2px;
    linkStyle 5 stroke:#007bff,stroke-width:2px;
    linkStyle 6 stroke:#007bff,stroke-width:2px;
    linkStyle 7 stroke:#00cc66,stroke-width:2px;
    linkStyle 8 stroke:#00cc66,stroke-width:2px;
    linkStyle 9 stroke:#a020f0,stroke-width:2px;
    linkStyle 10 stroke:#a020f0,stroke-width:2px;
    linkStyle 11 stroke:#00cc66,stroke-width:2px;

```
## 🧱 Lab Architecture Diagram (Full 180-Day Evolution)

```mermaid
graph TD
    A[Host Machine: Windows 11 / Kali Linux] --> B[Ubuntu Server 24.04 LTS - Wazuh SIEM + Suricata IDS]
    A --> C[Windows Server 2022 - Victim VM]
    A --> D[Kali Linux - Attacker VM]
    A --> F[pfSense Firewall - Traffic Control + Syslog Export]
    A --> G[Web Server - OWASP Juice Shop + ModSecurity WAF]
    A --> H[CI/CD Pipeline - GitHub Actions + SonarQube]

    F --> B
    F --> C
    F --> D
    F --> G

    D --> F
    F --> G
    G --> B
    C --> F
    F --> B
    B --> E[Wazuh / Splunk Dashboard]
    H --> G
    H --> B

    linkStyle 0 stroke:#007bff,stroke-width:2px
    linkStyle 1 stroke:#007bff,stroke-width:2px
    linkStyle 2 stroke:#007bff,stroke-width:2px
    linkStyle 3 stroke:#007bff,stroke-width:2px
    linkStyle 4 stroke:#007bff,stroke-width:2px
    linkStyle 5 stroke:#007bff,stroke-width:2px
    linkStyle 6 stroke:#007bff,stroke-width:2px
    linkStyle 7 stroke:#007bff,stroke-width:2px
    linkStyle 8 stroke:#ff0000,stroke-width:2px
    linkStyle 9 stroke:#007bff,stroke-width:2px
    linkStyle 10 stroke:#00cc66,stroke-width:2px
    linkStyle 11 stroke:#00cc66,stroke-width:2px
    linkStyle 12 stroke:#00cc66,stroke-width:2px
    linkStyle 13 stroke:#a020f0,stroke-width:2px
    linkStyle 14 stroke:#a020f0,stroke-width:2px
    linkStyle 15 stroke:#00cc66,stroke-width:2px
```
