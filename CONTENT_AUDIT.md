# Reporte de Auditoría de Contenido y Propuestas de Arquitectura — Fase 2A

> **Declaración de cumplimiento del alcance**: Ningún archivo fuente ni de configuración existente en el repositorio ha sido modificado durante esta fase. Este documento comprende únicamente el inventario mecánico, la extracción íntegra del contenido existente, la detección de inconsistencias y las propuestas de arquitectura para decisión de Juan.

---

## 1. Inventario de Contenido (Mecánico y Verificable)

Auditoría realizada sobre todos los archivos `.md` ubicados en `content/en/` y `content/es/`.

| Ruta del Archivo | Tipo de Página | Longitud Total (Palabras) | Longitud Cuerpo (Palabras) | Última Modificación (Git Log) | Equivalente en Otro Idioma | Estado de Paridad de Contenido |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| `content/en/_index.md` | Landing Page | 129 | 0 | 2026-05-07 | `content/es/_index.md` | **Difiere**: URLs de proyectos (`/projects/` vs `/es/projects/`), iconos (`circle-stack` vs `rectangle-stack`) y reglas de padding CSS adicionales en ES. |
| `content/es/_index.md` | Landing Page | 135 | 0 | 2026-05-07 | `content/en/_index.md` | **Difiere**: Enlaces de navegación bilingües y espaciados de bloque CTA. |
| `content/en/authors/_index.md` | Config Autores | 22 | 0 | 2026-05-06 | *Ninguno* | **Sin equivalente en ES**. Contiene ademá un error sintáctico (`build::`). |
| `content/en/authors/admin/_index.md` | Perfil Autor | 541 | 92 | 2026-05-07 | `content/es/authors/admin/_index.md` | **Difiere**: Redes sociales (WhatsApp y portapapeles en EN vs Teléfono/Ubicación en ES), etiquetas de habilidades y texto bio. |
| `content/es/authors/admin/_index.md` | Perfil Autor | 566 | 103 | 2026-05-07 | `content/en/authors/admin/_index.md` | **Difiere**: Redes sociales y traducción de habilidades. |
| `content/en/experience.md` | Sección / Landing | 25 | 0 | 2026-05-05 | `content/es/experience.md` | **Coincide**: Misma estructura de bloques `resume-experience`; difiere únicamente el título. |
| `content/es/experience.md` | Sección / Landing | 26 | 0 | 2026-05-05 | `content/en/experience.md` | **Coincide**: Estructura idéntica a EN. |
| `content/en/projects.md` | Sección / Landing | 50 | 0 | 2026-05-07 | `content/es/projects.md` | **Coincide**: Misma estructura de colección grid. |
| `content/es/projects.md` | Sección / Landing | 50 | 0 | 2026-05-07 | `content/en/projects.md` | **Coincide**: Estructura idéntica a EN. |
| `content/en/skills.md` | Sección / Landing | 32 | 0 | 2026-05-05 | `content/es/skills.md` | **Coincide**: Mismos bloques `resume-skills` y `resume-languages`. |
| `content/es/skills.md` | Sección / Landing | 33 | 0 | 2026-05-05 | `content/en/skills.md` | **Coincide**: Estructura idéntica a EN. |
| `content/en/project/bioinformatics-analyzer.md` | Proyecto | 55 | 18 | 2026-05-07 | `content/es/project/bioinformatics-analyzer.md` | **Difiere**: Título EN: "Molecular Diagnostics Data Structuring"; Tags EN: `Python, Molecular Diagnostics, Laboratory Data, Traceability`. |
| `content/es/project/bioinformatics-analyzer.md` | Proyecto | 96 | 38 | 2026-05-07 | `content/en/project/bioinformatics-analyzer.md` | **Difiere**: Título ES: "Automatización de Datos QC AU480"; Tags ES: `Python, Selenium, Pandas, QC Clínico, Automatización`. |
| `content/en/project/clinical-data-pipeline.md` | Proyecto | 65 | 17 | 2026-05-07 | `content/es/project/clinical-data-pipeline.md` | **Difiere**: EN se presenta como pipeline en `Python/Pandas`. |
| `content/es/project/clinical-data-pipeline.md` | Proyecto | 78 | 27 | 2026-05-07 | `content/en/project/clinical-data-pipeline.md` | **Difiere**: ES se presenta como automatización en `VBA/Excel`. |
| `content/en/project/lab-dashboard.md` | Proyecto | 56 | 19 | 2026-05-07 | `content/es/project/lab-dashboard.md` | **Coincide**: Mismo concepto ("Clinical KPI Dashboard" / "Dashboard de KPI Clínicos"). |
| `content/es/project/lab-dashboard.md` | Proyecto | 67 | 24 | 2026-05-07 | `content/en/project/lab-dashboard.md` | **Coincide**: Mismo concepto que en EN. |
| `content/es/project/laboratory-report-consolidation.md` | Proyecto | 66 | 22 | 2026-05-07 | *Ninguno* | **Sin equivalente en EN**: Este proyecto existe únicamente en la carpeta de español. |

---

## 2. Detección de Inconsistencias (Mecánico y Verificable)

Se detectaron las siguientes 6 inconsistencias específicas en el contenido actual:

### 1. Ausencia de Paridad en Proyectos y Configuraciones
- **Proyecto Húerfano**: `content/es/project/laboratory-report-consolidation.md` existe en español pero no posee archivo equivalente en `content/en/project/`.
- **Configuración de Autores Asimétrica**: `content/en/authors/_index.md` no tiene contraparte en `content/es/authors/_index.md`.

### 2. Contradicción de Stack Tecnológico entre Idiomas en Proyectos
- **`clinical-data-pipeline.md`**:
  - *Versión EN*: Título: "Clinical Data Pipeline for Laboratory Reporting". Tags: `Python`, `Pandas`, `Clinical Data`, `Data Cleaning`, `Reporting`. Summary: "Structured data pipeline concept for cleaning...".
  - *Versión ES*: Título: "Automatización de Datos de Laboratorio en Excel/CSV". Tags: `VBA`, `Excel`, `CSV`, `Reportes`, `Limpieza de Datos`. Summary: "Flujo de trabajo con Excel y VBA para consolidar...".
  - *Inconsistencia*: En inglés se atribuye a un desarrollo en **Python/Pandas**, mientras que en español se atribuye a **Excel/VBA**.
- **`bioinformatics-analyzer.md`**:
  - *Versión EN*: Título: "Molecular Diagnostics Data Structuring". Tags: `Python`, `Molecular Diagnostics`, `Laboratory Data`, `Traceability`. (Sin mención a Selenium ni al equipo AU480).
  - *Versión ES*: Título: "Automatización de Datos QC AU480". Tags: `Python`, `Selenium`, `Pandas`, `QC Clínico`, `Automatización`. (Centrado específicamente en el analizador Beckman Coulter AU480 y Selenium).

### 3. Divergencias en Enlaces y Metadata Social (`authors/admin/_index.md`)
- *Versión EN*: Incluye icono `clipboard` (copiar correo al portapapeles) e icono `phone` apuntando a enlace directo de WhatsApp (`https://wa.me/+527862607302...`).
- *Versión ES*: No incluye `clipboard`. Incluye icono `map-pin` (ubicación "México (GMT-6)" con URL vacía `''`) e icono `phone` con protocolo `tel:` (`tel:+527862607302`).

### 4. Desconexión Narrativa en la Biografía ("About Me") vs Experiencia Laboral
- En la biografía principal (`authors/admin/_index.md`), el cuerpo del texto expresa:
  > *"I am a biochemical engineer, with deep interest in exploring and exploiting the potential of molecular biology, specifically in axolotl regeneration and its applications in medicine and biotechnology..."*
- Sin embargo, el rol oficial definido en el frontmatter del mismo archivo y las funciones laborales en **Hospital MAC** señalan:
  > *Role: "Clinical Laboratory Automation & Data Analyst" / "Analista de Automatización y Datos para Laboratorio Clínico"*
- Hay una discrepancia entre la narrativa académica de investigación en regeneración de ajolote y el perfil profesional aplicado de automatización y análisis de datos clínicos.

### 5. Error Sintáctico en Archivo YAML
- En `content/en/authors/_index.md`, las líneas 3 y 6 utilizan sintaxis inválida `build::` (doble dos puntos `::` en lugar de `build:`).

### 6. Disparidad en Bloques de la Landing (`_index.md`)
- `content/en/_index.md` enlaza a `/projects/` usando el icono `circle-stack`.
- `content/es/_index.md` enlaza a `/es/projects/` usando el icono `rectangle-stack` y especifica reglas de padding CSS adicionales en la sección CTA.

---

## 3. Extracción de Contenido Profesional Íntegro (EN / ES)

A continuación se transcribe **íntegramente y sin alteraciones** todo el texto profesional existente en el repositorio.

---

### A. Perfil de Autor (`authors/admin/_index.md`)

#### Versión en Inglés (`content/en/authors/admin/_index.md`)

```yaml
title: Juan Hernández
first_name: Juan
last_name: Hernández
status:
  icon: 💻
superuser: true
highlight_name: true
role: Clinical Laboratory Automation & Data Analyst
organizations:
  - name: Hospital MAC
    url: ''
profiles:
  - icon: at-symbol
    url: "mailto:juan.hdz.9718@gmail.com"
    label: Contact Me
  - icon: clipboard
    icon_pack: hero
    link: "mailto:juan.hdz.9718@gmail.com"
    label: "juan.hdz.9718@gmail.com"
  - icon: brands/linkedin
    url: https://www.linkedin.com/in/yeidan18
    label: LinkedIn
  - icon: brands/github
    url: https://github.com/Danoop18
    label: GitHub
  - icon: phone
    url: 'https://wa.me/+527862607302/?text=Hi%2C%20I%20saw%20your%20professional%20portfolio%20and%20would%20like%20to%20contact%20you.'
    label: '+52 786 260 7302'

interests:
  - Laboratory Automation
  - Molecular Diagnostics
  - Clinical Data Pipelines
  - Quality Control Monitoring
  - Python/VBA Tools
  - Workflow Optimization

education:
  - area: M.Sc. Plant Biotechnology
    institution: CINVESTAV-UGA, Mexico
    date_start: 2021-08-01
    date_end: 2024-01-01
    summary: |
      Focus on molecular biology and biotechnology.
  - area: B.Sc. Biochemical Engineering
    institution: Tecnológico Superior de Cd. Hidalgo, Mexico
    date_start: 2017-01-01
    date_end: 2021-01-01
    summary: |
      Foundation in biochemical engineering and biological processes.

work:
  - position: Molecular Biology & Data Analyst
    company_name: Hospital MAC – Irapuato, Mexico
    company_url: ''
    company_logo: ''
    date_start: 2024-05-01
    date_end: ''
    summary: |
      - Performed molecular diagnostics workflows in a clinical laboratory environment.
      - Automated repetitive laboratory data processes using Python and Excel/VBA.
      - Improved structure, traceability, and consistency of operational laboratory data.
      - Supported quality control monitoring and reporting through cleaner data workflows.
      - Collaborated with clinical laboratory staff to identify manual bottlenecks and convert them into automation opportunities.
  - position: Junior Researcher
    company_name: CINVESTAV – Irapuato, Mexico
    company_url: ''
    company_logo: ''
    date_start: 2021-08-01
    date_end: 2023-08-01
    summary: |
      - Designed and executed molecular biology experiments for biotechnology research.
      - Structured experimental data for analysis, documentation, and technical reporting.
      - Developed Python scripts for data processing and visualization.
      - Translated laboratory needs into reproducible data workflows.

skills:
  - name: Laboratory
    items:
      - name: Molecular Diagnostics
        icon: beaker
      - name: Clinical Quality Control
        icon: check-badge
      - name: Laboratory Workflows
        icon: arrow-path
      - name: Sample Processing
        icon: circle-stack
  - name: Automation
    items:
      - name: Python
        icon: code-bracket
      - name: Excel VBA
        icon: command-line
      - name: Selenium
        icon: cursor-arrow-rays
      - name: Pandas
        icon: table-cells
  - name: Data
    items:
      - name: Data Cleaning
        icon: funnel
      - name: KPI Dashboards
        icon: presentation-chart-line
      - name: Report Automation
        icon: document-chart-bar
      - name: Process Monitoring
        icon: chart-bar
  - name: Tools
    items:
      - name: Streamlit
        icon: window
      - name: GitHub
        icon: brands/github
      - name: Excel
        icon: table-cells
      - name: Clinical analyzers
        icon: cpu-chip

languages:
  - name: Spanish
    percent: 100
    icon: check-badge
  - name: English (B2)
    percent: 75
```

**Texto Bio EN**:
> I am a biochemical engineer, with deep interest in exploring and exploiting the potential of molecular biology, specifically in axolotl regeneration and its applications in medicine and biotechnology. The main goal of my research is to discover fundamental mechanisms on cell biology which work synergistically to modulate development and regeneration of organisms. 
> 
> I have experience in molecular biology, confocal imaging, advanced microscopy, image analysis, and bioinformatics, as well as in the development of software for clinical data analysis.
> **My goal is to apply this knowledge to solve real-world problems.**

---

#### Versión en Español (`content/es/authors/admin/_index.md`)

```yaml
title: Juan Hernández
first_name: Juan
last_name: Hernández
status:
  icon: 💻
superuser: true
highlight_name: true
role: Analista de Automatización y Datos para Laboratorio Clínico
organizations:
  - name: Hospital MAC
    url: ''
profiles:
  - icon: at-symbol
    url: 'mailto:juan.hdz.9718@gmail.com'
    label: Contactar
  - icon: brands/linkedin
    url: https://www.linkedin.com/in/yeidan18
    label: LinkedIn
  - icon: brands/github
    url: https://github.com/Danoop18
    label: GitHub
  - icon: map-pin
    url: ''
    label: México (GMT-6)
  - icon: phone
    url: 'tel:+527862607302'
    label: '+52 786 260 7302'

interests:
  - Automatización de laboratorio
  - Diagnóstico molecular
  - Pipelines de datos clínicos
  - Monitoreo de control de calidad
  - Herramientas Python/VBA
  - Optimización de flujos de trabajo

education:
  - area: Maestría en Biotecnología de Plantas
    institution: CINVESTAV-UGA, México
    date_start: 2021-08-01
    date_end: 2024-01-01
    summary: |
      Enfoque en biología molecular y biotecnología.
  - area: Ingeniería Bioquímica
    institution: Tecnológico Superior de Cd. Hidalgo, México
    date_start: 2017-01-01
    date_end: 2021-01-01
    summary: |
      Fundamentos en ingeniería bioquímica y procesos biológicos.

work:
  - position: Analista de Datos y Biología Molecular
    company_name: Hospital MAC – Irapuato, México
    company_url: ''
    company_logo: ''
    date_start: 2024-05-01
    date_end: ''
    summary: |
      - Ejecución de flujos de trabajo de diagnóstico molecular en entorno de laboratorio clínico.
      - Automatización de procesos repetitivos de datos de laboratorio usando Python y Excel/VBA.
      - Mejora de estructura, trazabilidad y consistencia de datos operativos del laboratorio.
      - Apoyo al monitoreo y reporte de control de calidad mediante flujos de datos más limpios.
      - Identificación de cuellos de botella manuales y conversión de estos en oportunidades de automatización.
  - position: Investigador Junior
    company_name: CINVESTAV – Irapuato, México
    company_url: ''
    company_logo: ''
    date_start: 2021-08-01
    date_end: 2023-08-01
    summary: |
      - Diseño y ejecución de experimentos de biología molecular para investigación en biotecnología.
      - Estructuración de datos experimentales para análisis, documentación y reportes técnicos.
      - Desarrollo de scripts en Python para procesamiento y visualización de datos.
      - Traducción de necesidades de laboratorio en flujos de datos reproducibles.

skills:
  - name: Laboratorio
    items:
      - name: Diagnóstico molecular
        icon: beaker
      - name: Control de calidad clínico
        icon: check-badge
      - name: Flujos de trabajo de laboratorio
        icon: arrow-path
      - name: Procesamiento de muestras
        icon: circle-stack
  - name: Automatización
    items:
      - name: Python
        icon: code-bracket
      - name: Excel VBA
        icon: command-line
      - name: Selenium
        icon: cursor-arrow-rays
      - name: Pandas
        icon: table-cells
  - name: Datos
    items:
      - name: Limpieza de datos
        icon: funnel
      - name: Dashboards KPI
        icon: presentation-chart-line
      - name: Automatización de reportes
        icon: document-chart-bar
      - name: Monitoreo de procesos
        icon: chart-bar
  - name: Herramientas
    items:
      - name: Streamlit
        icon: window
      - name: GitHub
        icon: brands/github
      - name: Excel
        icon: table-cells
      - name: Analizadores clínicos
        icon: cpu-chip

languages:
  - name: Español (Nativo)
    percent: 100
  - name: Inglés (B2)
    percent: 75
```

**Texto Bio ES**:
> Soy ingeniero bioquímico y tengo un gran interés en explorar y aprovechar el potencial de la biología molecular, concretamente en la regeneración del ajolote y sus aplicaciones en medicina y biotecnología. El objetivo principal de mi investigación es descubrir los mecanismos fundamentales de la biología celular que actúan de forma sinérgica para modular el desarrollo y la regeneración de los organismos. 
> 
> Tengo experiencia en biología molecular, imagen confocal, microscopía avanzada, análisis de imágenes y bioinformática, así como en el desarrollo de software para el análisis de datos clínicos.
> **Mi objetivo es aplicar estos conocimientos para resolver problemas del mundo real.**

---

### B. Proyectos Individuales

#### 1. `bioinformatics-analyzer.md`

##### Versión EN (`content/en/project/bioinformatics-analyzer.md`):
- **Title**: Molecular Diagnostics Data Structuring
- **Summary**: Laboratory data structuring concept for organizing molecular diagnostics outputs into cleaner, more traceable records for review and reporting.
- **Tags**: `Python`, `Molecular Diagnostics`, `Laboratory Data`, `Traceability`
- **Date**: `2023-06-01T00:00:00Z`
- **Body Content**:
  > Laboratory data structuring concept for organizing molecular diagnostics outputs into cleaner, more traceable records for review and reporting.

##### Versión ES (`content/es/project/bioinformatics-analyzer.md`):
- **Title**: Automatización de Datos QC AU480
- **Summary**: Sistema de automatización con Python para extraer, limpiar y estructurar datos de control de calidad relacionados con flujos de trabajo del analizador clínico AU480. Diseñado para reducir manipulación manual repetitiva y apoyar el monitoreo del desempeño del laboratorio.
- **Tags**: `Python`, `Selenium`, `Pandas`, `QC Clínico`, `Automatización`
- **Date**: `2023-06-01T00:00:00Z`
- **Body Content**:
  > Sistema de automatización con Python para extraer, limpiar y estructurar datos de control de calidad relacionados con flujos de trabajo del analizador clínico AU480. Diseñado para reducir manipulación manual repetitiva y apoyar el monitoreo del desempeño del laboratorio.

---

#### 2. `clinical-data-pipeline.md`

##### Versión EN (`content/en/project/clinical-data-pipeline.md`):
- **Title**: Clinical Data Pipeline for Laboratory Reporting
- **Summary**: Structured data pipeline concept for cleaning, organizing, and preparing clinical laboratory records for reporting and process monitoring.
- **Tags**: `Python`, `Pandas`, `Clinical Data`, `Data Cleaning`, `Reporting`
- **Date**: `2023-01-01T00:00:00Z`
- **Body Content**:
  > Structured data pipeline concept for cleaning, organizing, and preparing clinical laboratory records for reporting and process monitoring.

##### Versión ES (`content/es/project/clinical-data-pipeline.md`):
- **Title**: Automatización de Datos de Laboratorio en Excel/CSV
- **Summary**: Flujo de trabajo con Excel y VBA para consolidar, limpiar y transformar datos de laboratorio provenientes de múltiples archivos, conservando estructura y reduciendo errores manuales en reportes.
- **Tags**: `VBA`, `Excel`, `CSV`, `Reportes`, `Limpieza de Datos`
- **Date**: `2023-01-01T00:00:00Z`
- **Body Content**:
  > Flujo de trabajo con Excel y VBA para consolidar, limpiar y transformar datos de laboratorio provenientes de múltiples archivos, conservando estructura y reduciendo errores manuales en reportes.

---

#### 3. `lab-dashboard.md`

##### Versión EN (`content/en/project/lab-dashboard.md`):
- **Title**: Clinical KPI Dashboard
- **Summary**: Interactive dashboard concept for monitoring clinical laboratory indicators, service demand, workflow distribution, and operational performance using structured data pipelines.
- **Tags**: `Python`, `Streamlit`, `Pandas`, `KPIs`, `Clinical Data`
- **Date**: `2024-01-01T00:00:00Z`
- **Body Content**:
  > Interactive dashboard concept for monitoring clinical laboratory indicators, service demand, workflow distribution, and operational performance using structured data pipelines.

##### Versión ES (`content/es/project/lab-dashboard.md`):
- **Title**: Dashboard de KPI Clínicos
- **Summary**: Concepto de dashboard interactivo para monitorear indicadores de laboratorio clínico, demanda de servicios, distribución de flujos de trabajo y desempeño operativo mediante datos estructurados.
- **Tags**: `Python`, `Streamlit`, `Pandas`, `KPI`, `Datos Clínicos`
- **Date**: `2024-01-01T00:00:00Z`
- **Body Content**:
  > Concepto de dashboard interactivo para monitorear indicadores de laboratorio clínico, demanda de servicios, distribución de flujos de trabajo y desempeño operativo mediante datos estructurados.

---

#### 4. `laboratory-report-consolidation.md` *(Exclusivo de Español)*

##### Versión ES (`content/es/project/laboratory-report-consolidation.md`):
- **Title**: Herramienta de Consolidación de Reportes de Laboratorio
- **Summary**: Herramienta de automatización para consolidar reportes de laboratorio desde múltiples archivos Excel, estandarizar registros y generar salidas más limpias para revisión operativa.
- **Tags**: `Python`, `Excel`, `Automatización`, `Procesamiento de Datos`
- **Date**: `2024-02-01T00:00:00Z`
- **Body Content**:
  > Herramienta de automatización para consolidar reportes de laboratorio desde múltiples archivos Excel, estandarizar registros y generar salidas más limpias para revisión operativa.

---

### C. Páginas de Sección (`projects.md`, `experience.md`, `skills.md`)

#### 1. `projects.md`
- **EN**: Title: "Projects" | Content Title: "Laboratory Automation Projects" | Content Text: "Selected work focused on clinical laboratory automation, quality control data, reporting workflows, and operational visibility."
- **ES**: Title: "Proyectos" | Content Title: "Proyectos de Automatización de Laboratorio" | Content Text: "Trabajo seleccionado enfocado en automatización de laboratorio clínico, datos de control de calidad, reportes y visibilidad operativa."

#### 2. `experience.md`
- **EN**: Title: "Experience & Education" | Block: `resume-experience`
- **ES**: Title: "Experiencia y Educación" | Block: `resume-experience`

#### 3. `skills.md`
- **EN**: Title: "Skills & Languages" | Blocks: `resume-skills` ("Skills"), `resume-languages` ("Languages")
- **ES**: Title: "Habilidades e Idiomas" | Blocks: `resume-skills` ("Habilidades"), `resume-languages` ("Idiomas")

---

## 4. Propuestas de Arquitectura de Información (Opciones A, B y C)

Se presentan **3 arquitecturas alternativas** sin imponer ninguna como la "correcta". La elección dependerá del objetivo profesional de Juan.

---

### OPCIÓN A — Arquitectura Orientada al Rol Clínico/Industrial ("Data & Automation Analyst")

#### Estructura Propuesta
1. **Hero / Homepage**:
   - Titular: *Analista de Automatización y Datos para Laboratorio Clínico*.
   - Mensaje principal: Automatización de flujos de laboratorio, reducción de carga manual, control de calidad y procesamiento de datos con Python/VBA.
2. **Sección de Experiencia**:
   - Destaca el rol en **Hospital MAC** (automatización de reportes, 600+ ensayos moleculares/mes, reducción del ~40% de carga manual).
   - Seguido del rol en **CINVESTAV** (desarrollo de scripts Python y estructuración de datos).
3. **Proyectos Clave**:
   - Organizados por impacto operativo: AU480 QC Automation, Consolidador de Reportes Excel/VBA, Dashboard de KPIs Clínicos.
4. **Habilidades**:
   - Agrupadas en: Automatización (Python, VBA, Selenium), Datos (Pandas, SQL/Limpieza, Dashboards) y Entorno Clínico (QC, Diagnóstico Molecular, Analizadores).

#### Pregunta Implícita que Responde Primero
> *"¿Qué problemas de datos, reportes y eficiencia en laboratorio clínico u operacional puede resolver Juan hoy mismo?"*

#### Priorización de Información
- **Prioriza**: Resultados prácticos de automatización, reducción de errores, trazabilidad de datos, Python, VBA, Streamlit, Hospital MAC.
- **Relega**: Investigación académica pura (regeneración de ajolote, biotecnología vegetal).

#### Trade-offs
- **Ventajas**:
  - Posicionamiento claro y de alto impacto para reclutadores en salud, TI médica, laboratorios de diagnóstico, empresas biotecnológicas industriales o roles de análisis de datos.
  - Mensaje coherente y sin distracciones entre la biografía, proyectos y experiencia.
- **Desventajas**:
  - Oculta/minimiza la profundidad científica académica y de laboratorio de investigación húmedo (wet-lab) en CINVESTAV.
- **Esfuerzo de Migración Estimado**: **Bajo** (requiere ajustar el texto de la bio "About Me" y alinear descripciones de proyectos).

---

### OPCIÓN B — Arquitectura Orientada al Perfil Híbrido Científico-Tecnológico ("Biomedical & Biotechnology Data Engineer")

#### Estructura Propuesta
1. **Hero / Homepage**:
   - Titular: *Ingeniero Bioquímico & M.Sc. en Biotecnología | Automatización de Datos & Diagnóstico Molecular*.
   - Mensaje principal: El puente entre la biología molecular de laboratorio y la ingeniería de software/datos.
2. **Secciones de Doble Enfoque**:
   - **Bloque 1: Diagnóstico y Biología Molecular**: Experiencia en ensayos de laboratorio, microscopía, calidad clínica e investigación (Hospital MAC + CINVESTAV).
   - **Bloque 2: Automatización y Software**: Scripts en Python, automatización VBA, bioinformática, dashboards en Streamlit.
3. **Proyectos Clave**:
   - Clasificados en dos pestañas/categorías: *Herramientas de Software/Datos* vs *Investigación y Diagnóstico Molecular*.

#### Pregunta Implícita que Responde Primero
> *"¿Cuál es la amplitud técnica y científica de Juan a lo largo de toda la cadena de datos biológicos y clínicos?"*

#### Priorización de Información
- **Prioriza**: La combinación única de wet-lab (biología bioquímica/molecular) + dry-lab (programación, datos y automatización).
- **Relega**: Ninguna área. Mantiene equilibrio entre academia e industria.

#### Trade-offs
- **Ventajas**:
  - Demuestra versatilidad multidisciplinaria ideal para empresas de biotecnología de vanguardia (Biotech R&D), secuenziación/genómica, startups MedTech o diagnóstico de precisión.
- **Desventajas**:
  - Corre el riesgo de parecer "demasiado amplio" si un empleador busca un perfil ultra-especializado (ej. solo programador backend o solo técnico de laboratorio).
- **Esfuerzo de Migración Estimado**: **Medio** (requiere estructurar taxonomías bilingües y reorganizar proyectos por categorías).

---

### OPCIÓN C — Arquitectura Orientada a Portfolio de Soluciones ("Problem-Solver / Project-First Portfolio")

#### Estructura Propuesta
1. **Hero / Homepage**:
   - Presentación ejecutiva breve y directa a la acción.
   - **Galería Destacada de Proyectos (Casos de Estudio)** en el centro de la página principal.
2. **Fichas de Caso de Estudio Expandidas**:
   - Cada proyecto deja de ser un resumen de 1 oración y se convierte en una página detallada estructurada en:
     - *Problema Operativo / Desafío*.
     - *Solución Desarrollada & Stack Tecnológico*.
     - *Capturas de Pantalla / Demostración / Repositorio GitHub*.
     - *Impacto y Resultados Medibles*.
3. **Experiencia y Educación como Respaldo**:
   - Secciones secundarias al final de la página o en subpáginas navegables.

#### Pregunta Implícita que Responde Primero
> *"¿Qué herramientas, sistemas y dashboards concretos ha construido Juan y cómo funcionan?"*

#### Priorización de Información
- **Prioriza**: Código, demostraciones de herramientas, arquitectura de software, dashboards en Streamlit y repositorios en GitHub.
- **Relega**: La narrativa curricular cronológica tradicional.

#### Trade-offs
- **Ventajas**:
  - Impacto visual inmediato y tangibilidad de habilidades. Excelente para clientes freelance, consultorías o roles donde se exige mostrar portafolios (código en GitHub, apps interactivas).
- **Desventajas**:
  - Exige redactar contenido nuevo y más extenso (capturas de pantalla, diagrama de arquitectura, explicación del problema) para cada caso de estudio.
- **Esfuerzo de Migración Estimado**: **Medio-Alto** (requiere ampliar significativamente la documentación interna de los proyectos).

---

## 5. Preguntas Abiertas para Decisión Humana (Juan)

Las siguientes decisiones estratégicas deben ser respondidas por Juan antes de iniciar la **Fase 2B**:

1. **Definición de Perfil y Posicionamiento**:
   - ¿Prefieres orientar tu CV hacia el perfil de **Analista de Automatización y Datos Clínicos** (Opción A), hacia un **Perfil Híbrido Científico-Biotecnológico** (Opción B), o enfocado en **Portfolio de Proyectos y Productos** (Opción C)?

2. **Alineación de la Biografía ("About Me")**:
   - Tu texto actual de biografía resalta la investigación en *regeneración de ajolote* y microscopía avanzada (enfoque académico/investigación), mientras que tu experiencia reciente en Hospital MAC resalta la *automatización de datos de laboratorio clínico y Python/VBA*. ¿Deseas actualizar la biografía para reflejar la automatización clínica o deseas conservar la narrativa de investigación biotecnológica?

3. **Resolución de Inconsistencias Tecnológicas en Proyectos**:
   - **`clinical-data-pipeline`**: ¿Es un desarrollo en Python/Pandas (versión EN) o en Excel/VBA (versión ES)? ¿O deben documentarse como dos proyectos/herramientas distintas?
   - **`bioinformatics-analyzer`**: ¿Es un script para el analizador Beckman Coulter AU480 con Selenium (versión ES) o una herramienta general de estructuración diagnóstica (versión EN)?
   - **`laboratory-report-consolidation`**: Este proyecto existe solo en español. ¿Se debe redactar su versión en inglés o fusionar con `clinical-data-pipeline`?

4. **Estrategia Lingüística y Paridad EN/ES**:
   - ¿Deseas mantener un sitio 100% bilingüe con estricta paridad de contenido entre inglés y español, o prefieres un idioma principal (ej. Inglés) con resumen en español?

5. **Estrategia del CV en PDF (`resume.pdf`)**:
   - ¿Deseas seguir subiendo un archivo PDF estático diseñado de forma independiente (`static/uploads/resume.pdf`), o te interesaría que en fases posteriores el PDF se genere/sincronice a partir del mismo contenido del sitio?

---

## 6. Confirmación de Estado del Repositorio y Entregable

Se ejecutó la verificación de estado sobre el árbol de trabajo mediante `git status`.

El único archivo nuevo generado durante esta fase es el presente documento `CONTENT_AUDIT.md`. Ningún archivo fuente del sitio ni de la configuración de Hugo ha sufrido cambios.

```text
PHASE 2A ANALYSIS: COMPLETE
```
