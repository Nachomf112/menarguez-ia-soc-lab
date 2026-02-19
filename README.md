🛡 Menarguez-IA SOC Lab

Laboratorio práctico de Security Operations Center (SOC) orientado a Blue Team, diseñado para simular un entorno empresarial real y entrenar tareas de detección, análisis y respuesta a incidentes.

🎯 Objectives

Simulate a realistic SOC environment

Practice detection engineering and event correlation

Align scenarios with MITRE ATT&CK

Build a technical Blue Team portfolio

Validate full monitoring pipeline

Agent → Manager → Indexer → Dashboard

🏗 Architecture Overview

Wazuh SIEM (Manager + Indexer + Dashboard)

Ubuntu Endpoint (Wazuh Agent)

Kali Linux (Attacker machine)

Controlled attack simulations

Structured documentation per scenario

🔴 Attack Scenarios
A01 – Nmap Reconnaissance

Objective
Generate reconnaissance traffic against the monitored endpoint.

Command

sudo nmap -sS -sV -O -Pn -T3 192.168.100.235


MITRE Mapping
T1046 – Network Service Discovery
https://attack.mitre.org/techniques/T1046/

Detection Notes
SYN scans may generate limited host-side logs because the TCP handshake is not fully completed.

A02 – SSH Brute Force Detection

Objective
Simulate repeated SSH authentication attempts using a non-existent user.

Command

for i in {1..10}; do ssh fakeuser@192.168.100.235; done


Wazuh Alerts Observed

Rule 5710 – Attempt to login using a non-existent user (Level 5)

Rule 5503 – PAM: User login failed (Level 5)

Rule 2502 – Multiple password failures (Level 10)

MITRE Mapping
T1110 – Brute Force
https://attack.mitre.org/techniques/T1110/

📊 Detection Summary
ID	Scenario	Severity	MITRE
A01	Reconnaissance	Low	T1046
A02	SSH Brute Force	High	T1110
🧠 Skills Demonstrated

SSH & PAM log analysis

Event correlation

Alert severity escalation

Threat hunting in OpenSearch / Wazuh

MITRE ATT&CK mapping

Structured security documentation

Git workflow management

🚀 Next Planned Scenarios

A03 – Hydra brute force simulation

A04 – File Integrity Monitoring detection

A05 – Privilege escalation simulation

A06 – Reverse shell detection

A07 – Persistence technique simulation

A08 – Custom Wazuh rule creation

📌 About

This repository reflects my practical training path as a SOC Analyst / Blue Team specialist, focused on detection engineering and real-world monitoring simulations.
