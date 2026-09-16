---
title: "Infraestructura de Servidor y Automatización Doméstica"
summary: "Infraestructura de servidor personal auto-hospedada con Home Assistant, monitoreo de red local y flujos de automatización en contenedores."
tags:
  - Home Assistant
  - Raspberry Pi
  - Linux
  - Docker
  - Automatización Doméstica
image:
  filename: /Homelab/homelab_portada.png
  focal_point: Smart
  preview_only: false
  alt_text: "Captura de imagen de mi dashboard principal de homelab"
categories:
  - Personal Lab
date: '2024-04-01T00:00:00Z'
---

### Estado
**Personal/En Desarrollo**

### Descripción General
Infraestructura de laboratorio personal configurada en hardware de bajo consumo (Raspberry Pi / nodo Linux) para auto-hospedar servicios de red local, rutinas de automatización e ingesta de datos de sensores.

### Servicios actuales
- Pi-Hole
- Unbound
- Nginx
- Mqtt
- Dashboard ligero
- Scripts Personalizados

##
<div style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px;">
  <img src="/uploads/Homelab_2.png" alt="Dashboard 1" style="width: 100%; border-radius: 15px;">
  <img src="/uploads/Homelab_1.png" alt="Dashboard 2" style="width: 100%; border-radius: 15px;">
  <img src="/uploads/Homelab_3.png" alt="Dashboard 3" style="width: 100%; border-radius: 15px;">
</div>   
<!-- <table>
  <tr>
    <td><img src="Screenshot_20260912_123827_Samsung Browser.png" alt="Servicio 1"></td>
    <td><img src="Screenshot_20260912_123840_Samsung Browser.png" alt="Servicio 2"></td>
    <td><img src="Screenshot_20260912_123818_Samsung Browser.png" alt="Servicio 3"></td>
  </tr>
</table>    -->

##

### Arquitectura y Herramientas
- **Home Assistant**: Hub central de automatización para control de dispositivos y monitoreo.
- **Docker**: Aislamiento de servicios en contenedores para utilidades locales y herramientas de red.
- **Linux / Raspberry Pi**: Servidor de bajo consumo operando 24/7.

### Enfoque
Privacidad de datos locales, confiabilidad del sistema y alertas automatizadas para métricas de red doméstica.
