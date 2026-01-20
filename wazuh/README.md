# 🛡️ Menarguez-IA SOC Lab — Wazuh Single Node (Histórico Técnico Real)

Este laboratorio documenta **la instalación real**, errores encontrados y solución definitiva  
de un **SOC Lab con Wazuh en modo single-node usando Docker**, integrando un **agente Ubuntu 24.04**.

> 📍 Proyecto: Menarguez-IA Solutions  
> 👤 Autor: Nacho Menárguez Fernández  
> 🌐 Web: https://menarguez-ia.com  
> 🧠 Objetivo: Blue Team · SOC · Automatización · Ciberseguridad práctica  

---

## 🧩 Arquitectura del laboratorio

**Manager / Dashboard / Indexer (Docker)**  
- Host: Kali Linux  
- Stack: Wazuh 4.14.2  
- Modo: Single-node  
- Orquestación: Docker Compose  

**Agente**
- Host: Ubuntu 24.04.3 LTS  
- Wazuh Agent: 4.14.2  
- IP: 192.168.100.235  

---

## 📁 Estructura usada


