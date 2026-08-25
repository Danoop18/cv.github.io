---
title: Herramienta de Consolidación de Reportes de Laboratorio
summary: Herramienta de automatización en Python que consolida datos semanales de múltiples fuentes Excel en una salida limpia y consistente, reduciendo errores de cálculo, formateo manual y ahorrando más de 8 horas de trabajo manual a la semana.
tags:
  - Python
  - Excel
  - KPIs
  - Automatización
  - Consolidación de Reportes
categories:
  - Engineering
date: '2024-02-01T00:00:00Z'
metric: "Ahorra más de 8 horas de trabajo manual a la semana mediante la semi-automatización del reporte semanal de KPIs"
---

### Problema

Los reportes semanales de KPIs requerían extraer datos manualmente de múltiples archivos Excel, aplicar fórmulas entre hojas y reformatear la salida para que coincidiera con una estructura estándar — cada semana. El proceso era lento, y cualquier error en una fórmula o desviación de formato introducía inconsistencias que había que encontrar y corregir antes de distribuir el reporte.

### Qué se construyó

Una herramienta de automatización en Python que lee datos de los archivos Excel fuente, consolida registros, aplica los cálculos requeridos y escribe la salida en una estructura consistente y preformateada, lista para revisión. El proceso que antes tomaba horas de trabajo manual corre en minutos.

### Tecnología

- **Python**: Lógica principal de procesamiento de datos y generación de salidas.
- **Pandas / OpenPyXL**: Carga de múltiples archivos, unión, cálculo y generación de salida Excel estructurada.
- **Excel**: Formato de los datos fuente y del reporte final.

### Cómo funciona

1. Los archivos fuente de la semana se colocan en el directorio de entrada designado.
2. El script carga y une registros de todos los archivos, valida la consistencia de campos y aplica los cálculos de KPIs.
3. Un reporte Excel limpio y consistentemente formateado se escribe en el directorio de salida, listo para revisión y distribución.

### Resultado

- **Métrica**: Ahorra más de 8 horas de trabajo manual a la semana mediante la semi-automatización del reporte semanal de KPIs.
- **Impacto**: Los errores de cálculo por ingreso manual de fórmulas fueron eliminados. El formato del reporte es consistente cada semana sin importar quién lo prepare. El tiempo del personal se redirige del ensamblaje del reporte al análisis y la toma de decisiones.

### Evidencia

- Herramienta en uso activo en el laboratorio clínico de Hospital MAC.
- Código mantenido en repositorio privado.
