# 🛡 Menarguez-IA SOC Lab

Laboratorio práctico de **Security Operations Center (SOC)** orientado a **Blue Team**, diseñado para simular un entorno empresarial real y entrenar tareas de detección, análisis y respuesta a incidentes.

---

## 🏢 Infraestructura simulada

- 🔐 SIEM (Wazuh)
- 🖥 Endpoints Linux (Ubuntu + Wazuh Agent)
- ⚔ Kali Linux (máquina atacante)
- 🌐 Servicios simulados (SSH, sistema)
- ⚙ Generación controlada de eventos
- 🎯 Casos de uso alineados con MITRE ATT&CK

---

## 🎯 Objetivos del laboratorio

- Simular un SOC realista basado en herramientas open-source
- Practicar detección, análisis y respuesta a incidentes
- Documentar casos reales alineados con MITRE ATT&CK
- Construir un portfolio técnico demostrable en GitHub
- Validar el pipeline completo:


---

## 🏗 Arquitectura (alto nivel)

- Wazuh SIEM (Manager + Indexer + Dashboard)
- Ubuntu Endpoint (Wazuh Agent)
- Kali Linux (Attacker Machine)
- Generación controlada de eventos
- Documentación estructurada por escenarios

---

# 🔴 Attack Scenarios

---

## 🔎 A01 – Nmap Reconnaissance

**Objetivo:**  
Generar tráfico de reconocimiento contra el endpoint monitorizado.

### 🖥 Comando utilizado (Kali)

```bash
sudo nmap -sS -sV -O -Pn -T3 192.168.100.235

🎯 MITRE Mapping

T1046 – Network Service Discovery

📝 Nota técnica

Los SYN scans (-sS) pueden generar registros limitados en el host porque el handshake TCP no se completa.

🔥 A02 – SSH Brute Force Detection

Objetivo:
Simular intentos repetidos de autenticación SSH usando un usuario inexistente.

🖥 Comando utilizado (Kali)
for i in {1..10}; do ssh fakeuser@192.168.100.235; done

🛡 Alertas detectadas en Wazuh

Rule 5710 → Attempt to login using a non-existent user (Level 5)

Rule 5503 → PAM: User login failed (Level 5)

Rule 2502 → Multiple password failures (Level 10)

🎯 MITRE Mapping

T1110 – Brute Force

📊 Resumen de detección
ID	Escenario	Severidad	MITRE
A01	Reconocimiento Nmap	Baja	T1046
A02	Fuerza bruta SSH	Alta	T1110
🧠 Capacidades demostradas

📄 Análisis de logs (sshd, PAM)

🔎 Correlación de eventos

🚨 Escalado de severidad (Level 5 → Level 10)

🧭 Threat hunting en OpenSearch / Wazuh

🎯 Mapeo MITRE ATT&CK

📚 Documentación estructurada de incidentes

🛠 Gestión de versiones con Git

🚀 Próximos escenarios

A03 – Hydra brute force simulation
A04 – File Integrity Monitoring (FIM) detection
A05 – Privilege escalation simulation
A06 – Reverse shell detection
A07 – Persistence technique simulation
A08 – Custom Wazuh rule creation

📌 Sobre este proyecto

Este repositorio forma parte de mi evolución profesional como SOC Analyst / Blue Team Specialist, enfocado en detección, correlación y monitorización de eventos en entornos simulados.

Proyecto desarrollado dentro del ecosistema Menarguez-IA Solutions.
