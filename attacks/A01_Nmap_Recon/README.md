# A01 - Nmap Reconnaissance (Ubuntu Agent)

## Objective
Generate reconnaissance traffic against the monitored Ubuntu endpoint and validate log ingestion / visibility in Wazuh.

## Target
- Ubuntu Wazuh Agent: 192.168.100.235

## Command (Kali)
```bash
sudo nmap -sS -sV -O -Pn -T3 -oN nmap_ubuntu_agent.txt 192.168.100.235
