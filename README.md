# 🛡 Menarguez-IA SOC Lab

Laboratorio práctico de **Security Operations Center (SOC)** orientado a **Blue Team**, diseñado para simular un entorno empresarial real y entrenar tareas de detección, análisis y respuesta a incidentes.

---

## 🏢 Infraestructura simulada

- 🔐 SIEM (Wazuh)  
- 🖥 Endpoints Linux  
- 🌐 Servicios simulados  
- ⚙ Generación controlada de eventos  
- 🎯 Casos de uso alineados con MITRE ATT&CK  

---

## 🎯 Objetivos del laboratorio

- Simular un SOC realista basado en herramientas open-source  
- Practicar detección, análisis y respuesta a incidentes  
- Documentar casos reales alineados con MITRE ATT&CK  
- Construir un portfolio técnico demostrable en GitHub  
- Validar el pipeline completo  


---

## 🏗 Arquitectura (alto nivel)

- Wazuh SIEM (Manager + Indexer + Dashboard)  
- Ubuntu Endpoint (Wazuh Agent)  
- Kali Linux (máquina atacante)  
- Generación controlada de eventos  
- Documentación estructurada por escenarios  

---

# 🔴 Attack Scenarios

---

## 🔎 A01 – Nmap Reconnaissance

**Objetivo:**  
Generar tráfico de reconocimiento contra el endpoint monitorizado.

**Comando utilizado (Kali):**

```bash
sudo nmap -sS -sV -O -Pn -T3 192.168.100.235
