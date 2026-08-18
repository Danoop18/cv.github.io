# Diseño de Arquitectura de Contenido — Fase 2B

> **Declaración de cumplimiento del alcance**: Este documento constituye exclusivamente el **diseño arquitectónico técnico y estructural** del sitio web del CV de Juan Hernández. Ningún archivo fuente del repositorio ha sido modificado. La implementación (Fase 2C) se ejecutará únicamente tras la aprobación explícita de Juan.

---

## 1. Identidad Aprobada y Jerarquía de Contenido (Insumo Fijo)

Las definiciones de marca personal y posicionamiento han sido fijadas previamente por Juan y se toman como insumo sin reinterpretación:

- **Framing Estratégico**:
  - *Identidad*: Perfil híbrido científico-tecnológico (Opción B del análisis previo).
  - *Presentación*: Portfolio de casos de estudio como evidencia tangible (Opción C).
  - *Experiencia*: Evidencia aplicada en el rol actual de Hospital MAC y CINVESTAV (Opción A).

- **Tagline Oficial en Inglés (EN)**:
  > *"Laboratory Automation Engineer — I build software, data workflows and analytical tools that turn laboratory processes into more reliable, traceable and scalable systems."*

- **Tagline Oficial en Español (ES)**:
  > *"Ingeniero de Automatización y Datos para Laboratorio — Desarrollo herramientas de software y flujos de datos que convierten procesos de laboratorio en sistemas más eficientes, trazables y reproducibles."*

- **Jerarquía Estricta de Secciones (Orden Informativo Fijo)**:
  1. **Qué hace**: Identidad, tagline y propuesta de valor profesional.
  2. **Qué ha construido**: Proyectos reales como evidencia primaria (*Case Studies*).
  3. **Dónde lo ha aplicado**: Experiencia laboral aplicada (Hospital MAC, CINVESTAV).
  4. **Qué sabe técnicamente**: Habilidades y herramientas (*Skills & Languages*).
  5. **Qué formación científica tiene**: Formación académica (M.Sc. Biotecnología, Ing. Bioquímica).

---

## 2. Mapa de Navegación y Distribución (Home vs. Páginas Internas)

La arquitectura de información se distribuye entre la página principal (**Home**) para impacto rápido y **Páginas Internas** para consulta detallada:

```text
[ HOME / LANDING PAGE ]
 ├── 1. HERO SECTION ──────────► Tagline Fijo + Bio Ejecutiva + CTAs (Descargar CV / Ver Proyectos)
 ├── 2. FEATURED PROJECTS ────► Grid de Case Studies Principales (Proyectos reales como evidencia)
 ├── 3. APPLIED EXPERIENCE ───► Resumen de roles en Hospital MAC & CINVESTAV
 ├── 4. TECHNICAL SKILLS ──────► Tarjetas de Habilidades (Automatización, Datos, Laboratorio)
 └── 5. EDUCATION ────────────► M.Sc. Biotecnología (CINVESTAV) & Ing. Bioquímica (ITSH)

[ PÁGINAS INTERNAS DE NAVEGACIÓN ]
 ├── /projects/ ──────────────► Galería completa de proyectos filtrables por stack y categoría
 │    └── /project/<id>/ ─────► Ficha individual de Case Study (Plantilla de 6 niveles)
 ├── /experience/ ────────────► Detalle cronológico de experiencia laboral y proyectos académicos
 └── /skills/ ────────────────► Matriz extendida de competencias técnicas, herramientas e idiomas
```

### Distribución Detallada por Página

| Sección | Ubicación en Home | Ubicación Interna | Contenido y Función |
| :--- | :--- | :--- | :--- |
| **1. Qué hace** | Hero Block (Bloque 1) | N/A | Tagline fijo bilingüe, botones de acción inmediata (Descargar `resume.pdf`, Contacto, GitHub, LinkedIn). |
| **2. Qué ha construido** | Preview Block (Bloque 2) | `/projects/` & `/project/<id>/` | Tarjetas con resúmenes de proyectos en Home; fichas de *Case Study* completas en rutas internas. |
| **3. Dónde lo ha aplicado** | Summary Block (Bloque 3) | `/experience/` | Resumen de posiciones principales en Home; historial y responsabilidades en `/experience/`. |
| **4. Qué sabe** | Summary Block (Bloque 4) | `/skills/` | Habilidades agrupadas (Laboratorio, Automatización, Datos, Herramientas) e Idiomas. |
| **5. Formación** | Summary Block (Bloque 5) | `/experience/#education` | M.Sc. Biotecnología de Plantas y B.Sc. Ingeniería Bioquímica. |

---

## 3. Taxonomía Final de Proyectos

Basado en la auditoría empírica del historial de Git y los archivos de contenido, la taxonomía oficial de proyectos queda definida de la siguiente manera:

```text
PROYECTOS DEL PORTFOLIO
 ├── au480-qc-automation ─────────────── (Anteriormente: bioinformatics-analyzer)
 ├── clinical-data-pipeline ──────────── [REQUIERE CONFIRMACIÓN DE JUAN: pipeline único o dos herramientas]
 ├── lab-dashboard ───────────────────── (Dashboard interactivo de KPI clínicos en Streamlit)
 └── laboratory-report-consolidation ─── (Consolidador de reportes operativos Excel/Python)
```

### Detalle de Proyectos y Resoluciones

1. **`au480-qc-automation`** *(Anteriormente `bioinformatics-analyzer`)*:
   - **Concepto Real**: Automatización de extracción, limpieza y estructuración de datos de control de calidad (QC) del analizador clínico Beckman Coulter AU480 mediante Python, Selenium y Pandas.
   - **Resolución**: Se renombra conceptualmente en el diseño para eliminar la denominación genérica "Bioinformatics Sequence Analyzer" y reflejar la herramienta real.

2. **`clinical-data-pipeline`**:
   - **Concepto Real**: Pipeline de datos para consolidación, limpieza y preparación de registros de laboratorio clínico.
   - **Estado de Ambigüedad**: `[REQUIERE CONFIRMACIÓN DE JUAN: pipeline único o dos herramientas]`. En el historial de Git se observa que la versión en inglés declara stack en `Python/Pandas` y la versión en español declara `Excel/VBA`. Si Juan confirma que fue una evolución del mismo proyecto (VBA → Python), se documentará como una sola historia de progresión técnica; si son herramientas distintas, se separarán.

3. **`lab-dashboard`**:
   - **Concepto Real**: Dashboard interactivo para el monitoreo de KPIs clínicos, demanda de servicios y flujos de trabajo mediante Streamlit y Pandas.
   - **Resolución**: Confirmado como proyecto independiente de visualización de datos.

4. **`laboratory-report-consolidation`**:
   - **Concepto Real**: Herramienta de automatización con Python y Excel para consolidación y estandarización de reportes de laboratorio de múltiples fuentes.
   - **Resolución**: Confirmado como proyecto independiente en la taxonomía (pendiente de creación de su versión traducida al inglés).

---

## 4. Plantilla de Case Study (Estructura de 6 Niveles)

Todos los proyectos dentro de `/project/<id>/` seguirán estrictamente la siguiente plantilla de 6 niveles:

```text
1. PROBLEMA ──────────► ¿Qué cuello de botella, error manual o ineficiencia existía en el laboratorio?
2. QUÉ SE CONSTRUYÓ ──► ¿Qué solución o herramienta de software se desarrolló?
3. TECNOLOGÍA ────────► Stack técnico utilizado (lenguajes, librerías, conectores).
4. CÓMO FUNCIONA ─────► Flujo de ejecución paso a paso (ingesta -> transformación -> salida).
5. RESULTADO ─────────► Impacto en legibilidad, trazabilidad o tiempo (métricas verificadas).
6. EVIDENCIA ─────────► Enlaces a código (GitHub), capturas, esquemas o demos.
```

### Aplicación Ilustrativa de la Plantilla (`au480-qc-automation`)

A continuación se muestra la aplicación de la plantilla sobre el proyecto **`au480-qc-automation`**, utilizando exclusivamente la información real existente en el repositorio sin inventar datos:

---

#### 1. PROBLEMA
> Manipulación manual repetitiva y fragmentada de los datos de control de calidad (QC) generados por el analizador clínico AU480, lo que generaba riesgo de error humano y dificultaba el seguimiento continuo del desempeño del laboratorio.

#### 2. QUÉ SE CONSTRUYÓ
> Sistema de automatización con Python para la extracción, limpieza y estructuración de datos de control de calidad relacionados con los flujos de trabajo del analizador clínico AU480.

#### 3. TECNOLOGÍA
> - `Python` (Procesamiento lógico de datos)
> - `Selenium` (Automatización de extracción e interacción)
> - `Pandas` (Limpieza, transformación y estructuración de matrices de datos)
> - `QC Clínico` (Dominio y reglas de validación de laboratorio)

#### 4. CÓMO FUNCIONA
> 1. Extracción automatizada de los registros brutos del analizador clínico AU480 mediante scripts de Selenium.
> 2. Limpieza y normalización de formatos heterogéneos de datos usando Pandas.
> 3. Generación de registros estandarizados y trazables para su revisión por parte del personal de laboratorio.

#### 5. RESULTADO
> `[MÉTRICA PENDIENTE DE VERIFICAR CON JUAN]`
> *(Nota de diseño: El case study mantiene total coherencia cualitativa resaltando la eliminación de manipulaciones manuales y la mejora de la trazabilidad operativa, incluso en ausencia de una cifra porcentual fijada).*

#### 6. EVIDENCIA
> - Repositorio de código: `[REQUIERE CONFIRMACIÓN DE JUAN: Enlace a repositorio GitHub o repositorio privado]`
> - Documentación de flujo: Integrado en el reporte operativo de laboratorio.

---

## 5. Opciones de Segmentación de Audiencia EN/ES

Para responder a las dos búsquedas de empleo que corre Juan (mercado local ES para laboratorios/biotech vs. mercado remoto internacional EN para data/Python), se diseñan **2 opciones de segmentación** con sus respectivos trade-offs:

### Opción 1: Simetría Estructural con Adaptación de Vocabulario Regional

- **Descripción**: Mantiene exactamente la misma estructura de bloques en inglés y en español. La diferenciación se logra mediante el **vocabulario técnico y las etiquetas (tags)** que cada mercado reconoce prioritariamente.
  - *Versión ES*: Enfatiza conceptos como *"Control de Calidad Clínico"*, *"Analizadores AU480"*, *"Diagnóstico Molecular"* y *"Estandarización de Procesos de Laboratorio"*.
  - *Versión EN*: Enfatiza conceptos como *"Laboratory Data Pipelines"*, *"Python/Pandas Automation"*, *"Data Traceability"* y *"Workflow Engineering"*.
- **Trade-offs**:
  - *Ventajas*: Mantenimiento de código sumamente sencillo en Hugo; no requiere lógica condicional entre idiomas; paridad 1:1 en las rutas del sitio.
  - *Desventajas*: No altera el orden de los proyectos si un reclutador remoto en inglés busca ver primero herramientas de Python puro antes que analizadores de laboratorio.

### Opción 2: Diferenciación de Énfasis y Prioridad Informativa por Idioma

- **Descripción**: Adapta la prioridad de las tarjetas de proyectos e historias según el idioma:
  - *Versión EN (Target: Remote Data/Python Jobs)*: Prioriza en las tarjetas del Home y en el grid superior los proyectos con mayor carga de desarrollo en Python (`lab-dashboard` en Streamlit y `clinical-data-pipeline` en Pandas).
  - *Versión ES (Target: Local Lab/Biotech Jobs)*: Prioriza en las tarjetas principales la experiencia aplicada en laboratorio (`au480-qc-automation`, `laboratory-report-consolidation` y flujos de diagnóstico de Hospital MAC).
- **Trade-offs**:
  - *Ventajas*: Maximiza la conversión y la relevancia inmediata para los dos tipos de reclutadores según el idioma en que naveguen.
  - *Desventajas*: Incrementa ligeramente la complejidad de la configuración de bloques en Hugo (`config/_default/menus` y filtros de colección).

---

## 6. Consolidado de Confirmaciones Pendientes (Para Juan)

Para facilitar la revisión por parte de Juan antes de proceder a la **Fase 2C (Implementación)**, se consolidan todos los puntos marcados como pendientes:

1. `[REQUIERE CONFIRMACIÓN DE JUAN: pipeline único o dos herramientas]`
   - Definir si `clinical-data-pipeline` es una sola historia de evolución técnica (Excel/VBA → Python/Pandas) o si son dos herramientas separadas.
2. `[REQUIERE CONFIRMACIÓN DE JUAN: creación de versión en inglés de laboratory-report-consolidation]`
   - Confirmar si se redacta la versión traducida al inglés de la "Herramienta de Consolidación de Reportes de Laboratorio".
3. `[REQUIERE CONFIRMACIÓN DE JUAN: selección de Opción 1 u Opción 2 de segmentación EN/ES]`
   - Seleccionar entre la Opción 1 (simetría de estructura con adaptación de vocabulario) o la Opción 2 (diferenciación de prioridad de proyectos por mercado).
4. `[MÉTRICA PENDIENTE DE VERIFICAR CON JUAN]` para `au480-qc-automation`
   - Indicar si existe una cifra verificada (ej. % de tiempo ahorrado o número de muestras procesadas) para incluir en el campo RESULTADO.
5. `[MÉTRICA PENDIENTE DE VERIFICAR CON JUAN]` para `clinical-data-pipeline`
   - Indicar si existe una cifra verificada de impacto.
6. `[MÉTRICA PENDIENTE DE VERIFICAR CON JUAN]` para `lab-dashboard`
   - Indicar si existe una cifra verificada de impacto.
7. `[MÉTRICA PENDIENTE DE VERIFICAR CON JUAN]` para `laboratory-report-consolidation`
   - Indicar si existe una cifra verificada de impacto.

---

## 7. Confirmación de Estado del Repositorio

Se verificó mediante `git status` que ningún archivo fuente de código, plantillas HTML, estilos CSS ni configuraciones de Hugo han sido modificados durante esta fase.

El único archivo generado es el presente documento `ARCHITECTURE_DESIGN.md`.

```text
PHASE 2B DESIGN: COMPLETE
```
