# 🧪 Proyecto de Redes LAN con VLANs, MSTP, VRRP y NAT (Huawei eNSP)



Este laboratorio fue desarrollado en Huawei eNSP como parte del Trabajo Práctico #4 del curso de Aplicaciones con Redes. El objetivo fue construir una red LAN con múltiples VLANs, alta disponibilidad mediante VRRP, y acceso a Internet usando NAT.



## 🎯 Objetivos del proyecto



- Configurar VLANs 9, 10, 11, 12 y 13 en switches capa 3

- Implementar VRRP entre Router1 y Router2 en la red 192.168.1.0/28

- Configurar interfaces SVI como gateways para cada VLAN

- Establecer enlaces troncales entre switches

- Configurar MSTP con dos instancias para optimizar el STP

- Implementar NAT dinámico (PAT) y NAT estático para acceso a Internet

- Validar conectividad con pings a 8.8.8.8 y pruebas de failover



## 🧱 Topología



La red incluye:

- 2 routers (Router1, Router2)

- 4 switches (SW1, SW2, SW3, SW4)

- 1 servidor Windows Server

- 3 PCs con Windows 7

- VLANs:  

- VLAN 9: 192.168.1.0/29  

- VLAN 10: 10.0.0.0/24  

- VLAN 11: 192.168.0.0/24  

- VLAN 12: 172.16.0.0/24  

- VLAN 13: 10.0.1.0/24



## 🔐 Alta disponibilidad



- VRRP configurado en los routers:

- VRID 1: R1 como máster

- VRID 2: R2 como máster

- SW1 y SW2 configurados con rutas por defecto hacia la IP virtual correspondiente

- VRRP también configurado en los switches para gateways de VLANs



## 🌉 Spanning Tree



- MSTP configurado:

- Instancia 1: VLANs 10 y 11 → SW1 como root

- Instancia 2: VLANs 12 y 13 → SW2 como root



## 🌐 NAT y pruebas



- PAT configurado en ambos routers para permitir acceso a Internet desde todas las VLANs

- NAT estático para el servidor Windows Server

- Pruebas de conectividad con pings a 8.8.8.8

- Pruebas de failover con pings continuos desde PCs y servidor



## 📂 Archivos incluidos



- `configs/`: Configuraciones CLI por dispositivo Huawei

- `topologia.png`: Imagen de la topología en eNSP

- `resultados_lab.pdf`: Capturas y análisis de pruebas



## 🧠 Aprendizajes



Este proyecto permitió reforzar conceptos clave como:

- Diseño de redes redundantes con VRRP

- Configuración de MSTP en entornos Huawei

- Validación de conectividad y análisis de tráfico

