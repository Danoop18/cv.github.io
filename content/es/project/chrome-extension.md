---
title: Herramienta de Registro Automatizado de Pacientes
summary: Herramienta de automatización web que gestiona el registro masivo de pacientes y el etiquetado de muestras en tomas empresariales, ahorrando más de 6 horas de captura manual por sesión y eliminando errores de etiquetado.
tags:
  - JavaScript
  - Automatización Web
  - Registro de Pacientes
categories:
  - Engineering
date: '2024-03-01T00:00:00Z'
metric: "Ahorra más de 6 horas de registro manual por sesión de toma empresarial y elimina errores de etiquetado"
---

### Problema

Las jornadas de toma de muestras empresariales requerían registrar listas extensas de pacientes e imprimir contenedores etiquetados en un tiempo reducido. Hacerlo manualmente a través del sistema web existente era lento, propenso a errores y ocupaba al personal durante horas en cada evento de recolección. Un error tipográfico en el registro de un paciente o un contenedor mal etiquetado tenía consecuencias para la identificación de la muestra.

### Qué se construyó

Una herramienta de automatización web que procesa listas de pacientes en lote e interactúa automáticamente con el sistema de registro: llenando formularios, enviando registros y disparando la generación de etiquetas sin captura manual por cada paciente.

### Tecnología

- **JavaScript**: Scripting del lado del cliente e interacción con el DOM para automatización de formularios.
- **Automatización web**: Llenado automático de formularios, envío de registros y activación de etiquetas sobre la interfaz web existente.

### Cómo funciona

1. Se prepara una lista de pacientes (nombre, ID, tipo de servicio) y se carga en la herramienta.
2. La automatización itera por la lista, llena el formulario de registro para cada paciente, envía el registro y dispara la generación de etiquetas.
3. El proceso corre de forma continua sin intervención manual hasta completar el lote completo.

### Resultado

- **Métrica**: Ahorra más de 6 horas de registro manual por sesión de toma empresarial y elimina errores de etiquetado de usuario.
- **Impacto**: El personal se redirige de la captura de datos a la atención directa al paciente durante los eventos de recolección. El riesgo de confusión entre paciente y etiqueta por errores de captura manual se eliminó para la porción automatizada del proceso.

### Evidencia

- Herramienta en uso activo para jornadas empresariales en Hospital MAC.
