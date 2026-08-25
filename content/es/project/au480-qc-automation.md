---
title: Automatización de Datos QC AU480
summary: Sistema de automatización en Python con Selenium y Pandas para extraer, limpiar y estructurar datos de control de calidad del analizador clínico AU480, eliminando la manipulación manual repetitiva.
tags:
  - Python
  - Selenium
  - Pandas
  - QC Clínico
  - Automatización
categories:
  - Engineering
date: '2023-06-01T00:00:00Z'
aliases:
  - /es/project/bioinformatics-analyzer/
metric: "Procesa lotes semanales con más de 100 analitos por día en aproximadamente 1 hora"
---

### Problema

Los datos de QC del analizador AU480 requerían extracción y manejo manual en múltiples sesiones cada semana. El proceso era repetitivo, propenso a errores y dificultaba el seguimiento consistente del desempeño del analizador. Cualquier variación en el manejo manual introducía ruido que ocultaba tendencias reales de QC.

### Qué se construyó

Un sistema de automatización en Python que se conecta a la fuente de datos del analizador mediante Selenium, extrae registros brutos de QC y los procesa a través de un pipeline de Pandas para producir salidas limpias y estructuradas, listas para revisión y monitoreo de desempeño.

### Tecnología

- **Python**: Lógica principal de scripting y procesamiento de datos.
- **Selenium**: Interacción automatizada con la interfaz de extracción de datos.
- **Pandas**: Limpieza, normalización y generación de salidas estructuradas.

### Cómo funciona

1. Selenium inicia una sesión automatizada y recupera registros brutos de QC desde la interfaz de datos del AU480.
2. Los registros se cargan en un DataFrame de Pandas y se limpian: se normalizan formatos inconsistentes, se eliminan entradas duplicadas y se validan los campos esperados.
3. El pipeline genera tablas estructuradas listas para revisión de QC y análisis de tendencias, sin reformateo manual.

### Resultado

- **Métrica**: Procesa lotes semanales con más de 100 analitos por día en aproximadamente 1 hora.
- **Impacto**: Eliminó la manipulación manual repetitiva de datos. El monitoreo de QC se volvió consistente y reproducible: el mismo proceso corre de la misma manera cada semana, sin importar quién lo ejecute.

### Evidencia

- Implementación activa en el laboratorio clínico de Hospital MAC.
- Código mantenido en repositorio privado.
