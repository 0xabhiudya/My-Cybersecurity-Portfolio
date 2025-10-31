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

---
## 🧭 Architecture Evolution (Phase 1 → 3)

Below diagrams illustrate the 180-day roadmap from a baseline SOC to a fully integrated DevSecOps architecture.

### 🎨 Color Legend  
| Color | Meaning | Example | 
|-------|---------|---------|
| 🔴 #ff0000 | Attack / Threat Paths | Attacker → Victim / Web Exploit  |
| 🟢 #00cc66 | Logs / Telemetry / Alerts | Syslog → SIEM → Dashboard  |
| 🔵 #007bff | Infrastructure / Neutral Links | VirtualBox Networks, Firewalls, CI/CD Links  |
---

## 🧩 Phase 1 – SOC & Network Monitoring

Objective: Establish a baseline Security Operations Center to collect, correlate, and visualize events.

Tools & Components:

🧠 Wazuh SIEM – Log correlation, agent management, alerting

🧱 Suricata IDS – Network intrusion detection and packet inspection

🪟 Windows Server 2022 (Victim) – Simulated target for event generation

🐧 Kali Linux (Attacker) – Red-team lab for penetration simulation

Expected Outputs:

Centralized alert dashboard (Wazuh → Splunk)

Event correlation between host logs & network IDS alerts

Verified end-to-end data flow from endpoint → SIEM

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
---

## 🧱 Phase 2 – Network Defense with pfSense

Objective: Introduce perimeter defense and log centralization to strengthen network visibility.

Tools & Components:

🔥 pfSense Firewall – VLAN segmentation, NAT, Syslog relay

🧩 Suricata + Wazuh Integration – IDS/IPS alerts to SIEM

📡 Syslog Server – Normalizes and routes logs to Wazuh / Splunk

Expected Outputs:

Filtered malicious traffic and IDS detections visible in SIEM

Firewall rule auditing and event logging to Wazuh

Baseline defense metrics (e.g., blocked packets, alert categories)

```mermaid
graph TD
    A[Host Machine: Windows 11 / Kali Linux] -->|VirtualBox| B[Ubuntu Server 24.04 LTS - Wazuh SIEM + Suricata IDS]
    A -->|VirtualBox| C[Windows Server 2022 - Victim VM]
    A -->|VirtualBox| D[Kali Linux - Attacker VM]
    A -->|VirtualBox| F[pfSense Firewall - Traffic Control + Syslog Export]

    subgraph Internal_Network
    F --> B
    F --> C
    F --> D
    end

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
---

## ⚙️ Phase 3 – AppSec + DevSecOps Integration

Objective: Extend visibility into application and pipeline layers for proactive security automation.

Tools & Components:

🧱 OWASP Juice Shop – Deliberately vulnerable web app

🛡️ ModSecurity WAF – Web-layer defense integrated with pfSense / Wazuh

⚙️ GitHub Actions + SonarQube – Automated SAST + pipeline security scans

Expected Outputs:

WAF event ingestion and correlation in Wazuh / SIEM

Automated SAST alerts during build and deployment

End-to-end visibility: code → app → network → SIEM → dashboard

```mermaid
graph TD
    A[Host Machine: Windows 11 / Kali Linux] -->|VirtualBox| B[Ubuntu Server 24.04 LTS - Wazuh SIEM + Suricata IDS]
    A -->|VirtualBox| F[pfSense Firewall - Traffic Control + Syslog Export]
    A -->|VirtualBox| G[Web Server - OWASP Juice Shop + ModSecurity WAF]
    A -->|Cloud| H[CI/CD Pipeline - GitHub Actions + SonarQube]

    subgraph Internal_Network
    F --> B
    F --> G
    end

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
---

## 🧱 Lab Architecture Diagram (Full 180-Day Evolution)

```mermaid
graph TD
    %% --- Phase 1: SOC Core ---
    A[Host Machine: Windows 11 / Kali Linux] -->|VirtualBox| B[Ubuntu Server 24.04 LTS - Wazuh SIEM + Suricata IDS]
    A -->|VirtualBox| C[Windows Server 2022 - Victim VM]
    A -->|VirtualBox| D[Kali Linux - Attacker VM]

    %% --- Phase 2: Network Defense ---
    A -->|VirtualBox| F[pfSense Firewall - Traffic Control + Syslog Export]

    %% --- Phase 3: AppSec + DevSecOps ---
    A -->|VirtualBox| G[Web Server - OWASP Juice Shop + ModSecurity WAF]
    A -->|Cloud / Remote| H[CI/CD Pipeline - GitHub Actions + SonarQube]

    %% --- Network Layout ---
    subgraph Internal_Network
        F <--> B
        F <--> C
        F <--> D
        F <--> G
    end

    %% --- Data + Attack Flows ---
    D -->|Attack Traffic| F
    F -->|Filtered Traffic| G
    G -->|WAF Alerts to SIEM| B
    C -->|Event Logs| F
    F -->|Syslog + IDS Alerts| B
    B -->|Correlated Events| E[Wazuh / Splunk Dashboard]
    H -->|SAST Reports + Deployments| G
    H -->|DevSecOps Alerts| B
    B -->|Alerts to Dashboard| E

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
---
