---
title: "Pipeline de Datos Clínicos: de Excel/VBA a Python"
summary: "Evolución de un flujo de trabajo de datos de laboratorio: iniciando con macros de Excel/VBA para la consolidación de reportes y reconstruido como un pipeline Python/Pandas para un procesamiento de datos más confiable y mantenible."
tags:
  - Python
  - Pandas
  - VBA
  - Excel
  - Pipeline de Datos
  - Reportes
categories:
  - Engineering
date: '2023-01-01T00:00:00Z'
---

### Problema

Los registros de laboratorio se consolidaban manualmente desde múltiples hojas de cálculo en cada ciclo de reporte. El proceso dependía de operaciones de copiar-pegar, aplicación manual de fórmulas y ajustes de formato que se repetían desde cero en cada ocasión. Los errores se acumulaban en silencio y rastrear su origen era difícil.

### Qué se construyó

El flujo de trabajo pasó por dos etapas. Primero, un conjunto de macros Excel/VBA automatizó los pasos de formato y consolidación más repetitivos dentro del entorno de hojas de cálculo existente. A medida que los requisitos crecieron y el volumen de datos aumentó, el proceso se reconstruyó como un pipeline Python/Pandas que realiza la misma consolidación y limpieza de forma más confiable, scripteable y mantenible.

### Tecnología

**Etapa 1 — Excel/VBA:**
- Macros de Excel para estandarización de formato y consolidación básica de campos entre hojas.
- Scripts VBA para automatizar pasos manuales repetitivos sin cambiar el flujo de trabajo basado en hojas de cálculo.

**Etapa 2 — Python/Pandas:**
- Scripts de Python reemplazan el ensamblaje manual de datos.
- Pandas para limpieza estructurada, validación y transformación de registros de múltiples fuentes.

### Cómo funciona

1. Los registros brutos de múltiples archivos se cargan en un único contexto de procesamiento (hoja de cálculo o script, según la etapa).
2. Las inconsistencias de formato se detectan y corrigen: formatos de fecha, nomenclatura de campos, filas vacías y desajustes de columnas.
3. Los datos limpios y validados se escriben en una salida única estructurada para reporte operativo.

### Resultado

- **Impacto**: Reducción del riesgo de errores manuales en la preparación de reportes. La transición de VBA a Python hizo el proceso más fácil de auditar, modificar y transferir — la lógica vive en código, no en referencias de celdas.
- La métrica de este proyecto es cualitativa: el valor está en la reproducibilidad y la reducción de errores, no en un único número medible.

### Evidencia

- Ambas etapas implementadas en Hospital MAC.
- Macros VBA y scripts Python mantenidos en repositorio privado.
