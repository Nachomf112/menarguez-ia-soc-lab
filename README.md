🛡 Menarguez-IA SOC Lab

Laboratorio práctico de Security Operations Center (SOC) orientado a Blue Team, diseñado para simular un entorno empresarial real y entrenar tareas de detección, análisis y respuesta a incidentes.

Este laboratorio reproduce una infraestructura simplificada de empresa utilizando Wazuh (SIEM/XDR) y endpoints Linux monitorizados.

🎯 Objetivos del laboratorio

Simular un SOC realista basado en herramientas open-source

Practicar detección, análisis y correlación de eventos

Documentar casos reales alineados con MITRE ATT&CK

Construir un portfolio técnico demostrable en GitHub

Validar el pipeline completo:
Agent → Manager → Indexer → Dashboard

🏗 Arquitectura (alto nivel)

Wazuh SIEM (Manager + Indexer + Dashboard)

Endpoint Linux (Ubuntu) con Wazuh Agent

Máquina atacante (Kali Linux)

Generación controlada de eventos de seguridad

Documentación estructurada por escenarios

🔴 Attack Scenarios & Detection Summary
ID	Attack Scenario	Detection Rules Observed	Severity	MITRE ATT&CK
A01	Nmap Reconnaissance	Limited host-side logs	Low	T1046
A02	SSH Brute Force	5710, 5503, 2502	High	T1110
🧠 Detection Capabilities Demonstrated

SSH authentication monitoring

PAM log ingestion and parsing

Brute force correlation

Severity escalation (Level 5 → Level 10)

Non-existent user detection

SOC workflow validation

📁 Project Structure
menarguez-ia-soc-lab/
│
├── attacks/
│   ├── A01_Nmap_Recon/
│   │   ├── nmap_ubuntu_agent.txt
│   │   └── README.md
│   │
│   └── A02_SSH_BruteForce/
│       ├── README.md
│       └── evidence/
│
├── wazuh/
├── docs/
└── README.md

🔎 A01 – Nmap Reconnaissance

Objective:
Generate reconnaissance traffic against the monitored endpoint.

Command used (Kali):

sudo nmap -sS -sV -O -Pn -T3 192.168.100.235


Technical Note:
SYN scans (-sS) may generate limited host logs because the TCP handshake is not fully completed.

MITRE Mapping:
T1046 – Network Service Discovery
https://attack.mitre.org/techniques/T1046/

🔥 A02 – SSH Brute Force Detection

Objective:
Simulate repeated SSH authentication attempts using a non-existent user.

Attack Command (Kali):

for i in {1..10}; do ssh fakeuser@192.168.100.235; done


Detected Rules (Wazuh):

Rule 5710 – Attempt to login using a non-existent user (Level 5)

Rule 5503 – PAM: User login failed (Level 5)

Rule 2502 – Multiple password failures (Level 10)

MITRE Mapping:
T1110 – Brute Force
https://attack.mitre.org/techniques/T1110/

📊 Skills Demonstrated

Log analysis (auth.log, sshd, PAM)

Event correlation

Alert severity interpretation

Threat hunting using OpenSearch / Wazuh

MITRE ATT&CK mapping

Security documentation best practices

Git workflow (structured commits, version control)

🚀 Next Planned Scenarios

A03 – Hydra brute force simulation

A04 – File Integrity Monitoring (FIM) detection

A05 – Privilege escalation simulation

A06 – Reverse shell detection

A07 – Persistence technique simulation

A08 – Custom Wazuh rule creation

📌 About This Project

This repository is part of my continuous development as a SOC Analyst / Blue Team specialist, focused on practical detection engineering and security monitoring.
