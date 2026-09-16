---
title: Herramienta de Registro Automatizado de Pacientes
summary: Herramienta de automatización web que gestiona el registro por lotes de pacientes y el etiquetado de muestras en tomas empresariales, ahorrando más de 8 horas de captura manual por sesión y eliminando errores de nombre y etiquetado.
tags:
  - JavaScript
  - Automatización Web
  - Registro de Pacientes
image:
  filename: proyectos/extension_portada.png
  focal_point: Smart
  preview_only: false
  all_text: "HTML cover page for the batch clinical record extension."
categories:
  - Engineering
date: '2024-03-01T00:00:00Z'
metric: "Ahorra más de 8 horas de registro manual por sesión en tomas empresariales y elimina errores de registro en datos personales y etiquetado"
---

### Problema

Las jornadas de toma de muestras empresariales requieren registrar y etiquetar más de 100 muestras en un tiempo reducido. Hacerlo manualmente a través del LIMS web existente era lento, no permitía carga masiva y era propenso a errores; además, ocupaba al personal, la etiquetadora y las terminales durante horas en cada evento. Un error tipográfico en el registro de una persona o un contenedor mal etiquetado provocaba pérdida de trazabilidad de la muestra, retrasos en la corrección y cruces erróneos de datos personales.

### Qué se construyó

Una herramienta de automatización web que procesa listas de pacientes en lote e interactúa automáticamente con el sistema de registro: llena formularios, envía registros y dispara la generación de etiquetas sin captura manual por cada paciente.

### Tecnología

- **JavaScript**: Interacción con el DOM para automatizar formularios, envío de registros y activación de etiquetas sobre la interfaz web existente del LIMS.
- **Automatización web**: Llenado automático de formularios, envío de registros y activación de etiquetas sobre la interfaz web existente.

### Cómo funciona

1. Se prepara una lista de pacientes (nombre, fecha de nacimiento, estudios a realizar, ID, género) y se carga en la herramienta.
2. La automatización itera por la lista, realiza comprobaciones contra la base de datos del LIMS, llena el formulario de registro para cada paciente, envía el registro y dispara la generación de etiquetas.
3. El proceso corre de forma continua sin intervención manual hasta completar el lote.

### Resultado

- **Métrica**: Ahorra más de 8 horas de registro manual por sesión de toma empresarial y elimina errores de etiquetado por captura manual. Al usar una sola terminal en segundo plano, el técnico puede interactuar libremente en una segunda sesión ó atendender pacientes durante el proceso.

- **Impacto**: EEl personal se redirige de la captura de datos a la atención directa al paciente durante los eventos de recolección. El riesgo de confusión entre paciente y etiqueta por errores de captura se elimina en la parte automatizada del proceso.

### Evidencia

- Herramienta en uso activo para jornadas empresariales en Hospital MAC.
