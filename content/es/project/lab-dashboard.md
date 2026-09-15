---
title: Dashboard de KPI Clínicos y Bitácora Digital
summary: Aplicación Streamlit que debería reemplazar el registro manual de múltiples usuarios por una bitácora digital estructurada con consulta y comparación de registros en tiempo real.
tags:
  - Python
  - Streamlit
  - Pandas
  - KPIs
  - Bitácora Digital
image:
  Filename: /proyectos/lims_cover.png
  focal_point: Smart
  preview_only: false
  All_text: "Aplicación de bitacora mvp para el registro y analisis de pacientes local, reemplazo de la base de datos comercial"
categories:
  - Engineering
date: '2024-01-01T00:00:00Z'
metric: "Sistema de bitácora completamente digital — elimina el registro manual de múltiples usuarios y agiliza la búsqueda y cotejo de registros de local, sin latencia con alto potencial de expansión"
---
### Estado
**No implementado**

### Problema

Los registros del laboratorio se mantienen en bitácoras físicas y hojas de cálculo desconectadas y actualizadas por múltiples personas. Buscar un registro específico implica revisar páginas manualmente. Cruzar datos entre fechas, analistas o servicios no es viable en la operación diaria. No existé un lugar único donde ver qué ocurre en el laboratorio en un momento dado.

### Qué se construyó

Una aplicación Streamlit interactiva que funciona como bitácora digital estructurada y como dashboard de KPI operativos. Con potencial de expandise a LIMS operativo. El personal ingresa registros a través de una interfaz de formulario intuitiva y completa; la aplicación almacena, organiza y muestra los datos de forma que la búsqueda, el filtrado y la comparación sean inmediatos sin recargas de web inecesarias y estables.

### Tecnología

- **Python**: Lógica de datos del backend y estructura de la aplicación.
- **Streamlit**: Interfaz web interactiva para ingreso de datos y visualización.
- **Pandas**: Estructuración, filtrado y agregación de KPIs.

### Cómo funciona

1. El personal del laboratorio ingresa registros diarios mediante un formulario estructurado en la interfaz web (tipo de servicio, analista, resultado, fecha, observaciones).
2. Las entradas se almacenan e indexan para que cualquier registro pueda recuperarse por fecha, analista o servicio sin revisar páginas físicas.
3. La capa de dashboard agrega las entradas en KPIs operativos: volumen diario por servicio, tasas de aprobación de QC, distribución de carga de trabajo entre analistas.

### Resultado

- **Métrica**: Sistema de bitácora completamente digital — elimina el registro manual de múltiples usuarios y agiliza la búsqueda y cotejo de registros.
- **Impacto**: El laboratorio dejaría de mantener registros físicos y digitales en paralelo. Los datos ingresados una vez son consultables de inmediato. La toma de decisiones basada en tendencias operativas se volviría posible sin preparación manual de reportes.

### Evidencia

- ~~Desplegado en el laboratorio clínico de Hospital MAC~~.
- Código mantenido en repositorio privado.
