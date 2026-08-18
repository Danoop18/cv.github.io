# Guía de Mantenimiento y Gestión de Contenido (`CONTENT_GUIDE.md`)

Esta guía explica de forma práctica y paso a paso cómo gestionar, actualizar y agregar contenido al sitio web del CV de **Juan Hernández** sin necesidad de modificar plantillas HTML, estilos CSS ni código de Hugo.

---

## 1. Estructura General del Contenido

El sitio utiliza una arquitectura bilingüe estandarizada basada en archivos Markdown planos (`.md`):

```text
content/
 ├── en/                          <-- Contenido en Inglés
 │   ├── _index.md                <-- Landing Page (Hero, Secciones, CTAs)
 │   ├── experience.md            <-- Vista de Experiencia
 │   ├── projects.md              <-- Grid Galería de Proyectos
 │   ├── skills.md                <-- Vista de Habilidades e Idiomas
 │   ├── authors/admin/_index.md  <-- Perfil del Autor, Experiencia, Skills y Educación
 │   └── project/                 <-- Proyectos / Case Studies en Inglés
 │       ├── au480-qc-automation.md
 │       ├── chrome-extension.md
 │       ├── clinical-data-pipeline.md
 │       └── lab-dashboard.md
 │
 └── es/                          <-- Contenido en Español
     ├── _index.md
     ├── experience.md
     ├── projects.md
     ├── skills.md
     ├── authors/admin/_index.md
     └── project/                 <-- Proyectos / Case Studies en Español
         ├── au480-qc-automation.md
         ├── chrome-extension.md
         ├── clinical-data-pipeline.md
         ├── lab-dashboard.md
         └── laboratory-report-consolidation.md
```

---

## 2. Decisiones de Formato (Archivos Planos vs. Page Bundles)

Para maximizar la mantenibilidad y simplicidad, todos los proyectos utilizan **archivos Markdown planos** directamente dentro de `content/<lang>/project/nombre-proyecto.md`.

- **¿Por qué archivos planos?**: No requieren crear subcarpetas complejas por cada proyecto. Se editan directamente y son consumidos automáticamente por las galerías y listas de Hugo.
- **¿Cuándo usar Page Bundles (`project/nombre/index.md`)?:** Únicamente si un proyecto requiere una galería con múltiples imágenes locales privadas que no se compartan con el resto del sitio.

---

## 3. Cómo Agregar un Nuevo Proyecto (Paso a Paso)

Para añadir un nuevo proyecto al portfolio, sigue este procedimiento:

### Paso 1: Crear los archivos de contenido
Crea una copia plana en **ambos idiomas**:
- En inglés: `content/en/project/mi-nuevo-proyecto.md`
- En español: `content/es/project/mi-nuevo-proyecto.md`

> **Política de paridad EN/ES**: La norma del sitio es "mismo portfolio en ambos idiomas, distinto énfasis". Un proyecto puede lanzarse primero en un idioma si hay restricción de tiempo, pero **debe quedar registrado como traducción pendiente** en la sección 8 de esta guía. La asimetría permanente no es el estado final aceptable.

### Paso 2: Configurar el Front Matter Mínimo
Copia y completa la siguiente plantilla al inicio del archivo:

```yaml
---
title: "Título del Proyecto"
summary: "Descripción breve de 1-2 oraciones del proyecto para las tarjetas de la galería."
tags:
  - Python
  - Automatización
  - Laboratorio
date: '2024-06-01T00:00:00Z'
metric: "Métrica o resultado clave verificable (ej. Ahorro de 5 hrs manuales a la semana)."
---

### Problema
Descripción del cuello de botella, error manual o ineficiencia operativa que existía.

### Qué se construyó
Descripción de la solución de software o herramienta desarrollada.

### Tecnología
- **Lenguaje/Framework**: Herramientas utilizadas (Python, VBA, Streamlit, etc.).
- **Librerías**: Pandas, Selenium, etc.

### Resultado
- **Métrica**: Métrica real verificada.
- **Impacto**: Beneficio cualitativo u operativo en el laboratorio.
```

> **Nota sobre comillas en `summary`**: Si la descripción del `summary` contiene dos puntos seguidos de espacio (`: `), encierra siempre el texto entre comillas dobles `"..."` para evitar errores en YAML.

---

## 4. Dónde Modificar Experiencia, Habilidades y Biografía

Toda la información del perfil profesional se centraliza en un único archivo por idioma:

- **Inglés**: `content/en/authors/admin/_index.md`
- **Español**: `content/es/authors/admin/_index.md`

### Para editar Experiencia Laboral (`work`):
Modifica el bloque `work:` dentro del front matter de `authors/admin/_index.md`:

```yaml
work:
  - position: Analista de Datos y Biología Molecular
    company_name: Hospital MAC – Irapuato, México
    date_start: 2024-05-01
    date_end: ''
    summary: |
      - Ejecución de flujos de trabajo de diagnóstico molecular...
```

### Para editar Habilidades (`skills`):
Modifica la lista `skills:` dentro del front matter de `authors/admin/_index.md`.

### Para editar la Biografía ("Acerca de mí"):
Modifica el texto en Markdown que se encuentra **debajo del segundo `---`** en `authors/admin/_index.md`.

---

## 5. Gestión de Assets e Imágenes

- **PDF del CV descargable**: Ubicado en `static/uploads/resume.pdf`. Para actualizar el CV en PDF, simplemente reemplaza este archivo conservando el nombre `resume.pdf`.
- **Fotografía de Perfil (Avatar)**: Ubicada en `content/en/authors/admin/avatar.png` y `content/es/authors/admin/avatar.png`.
- **Imágenes de Proyectos o Ilustraciones**: Guardar en `static/uploads/` o `assets/media/` y hacer referencia mediante `/uploads/nombre-imagen.png`.

---

## 6. Procedimiento de Verificación (Comandos)

Después de realizar cualquier cambio o agregar un nuevo proyecto, ejecuta los siguientes comandos en la terminal desde la raíz del proyecto:

1. **Sincronización de Dependencias**:
   ```bash
   npm ci
   ```
2. **Compilación del Sitio Hugo**:
   ```bash
   hugo --minify
   ```

Si `hugo --minify` finaliza con `Total in X ms` y código de salida 0, el sitio está listo para desplegarse.

---

## 7. Ejemplo de Mantenibilidad (Caso Piloto: `clinical-data-pipeline`)

Este proyecto sirve como demostración práctica de cómo se gestiona una historia de evolución técnica en el repositorio:

- **Archivo**: `content/es/project/clinical-data-pipeline.md`
- **Evolución representada**: Excel/VBA → Python/Pandas.
- **Procedimiento aplicado**: Se integraron ambas fases tecnológicas en las secciones `Qué se construyó` y `Tecnología` dentro de un único archivo plano `.md`, evitando duplicar páginas o crear configuraciones complejas.

---

## 8. Política de Paridad EN/ES y Traducciones Pendientes

### Principio
El sitio mantiene el principio: **mismo portfolio en ambos idiomas, distinto énfasis por audiencia**. Esto significa:

- **Asimetría temporal aceptable**: Un proyecto puede existir primero en un idioma si hay restricción de tiempo. Debe quedar registrado en la tabla de abajo y traducirse en la siguiente iteración de contenido.
- **Asimetría permanente sin seguimiento**: **NO** es la política del sitio. No tener una versión traducida sin anotarla como pendiente equivale a dejar el portfolio fragmentado sin control.

### Traducciones Pendientes Activas

| Proyecto | Existe en EN | Existe en ES | Pendiente | Fase objetivo |
| :--- | :---: | :---: | :--- | :--- |
| `laboratory-report-consolidation` | ❌ | ✅ | Crear `content/en/project/laboratory-report-consolidation.md` | Fase 2D (Copywriting) |
| `chrome-extension` | ✅ | ✅ | — | Completo |

> **Instrucción**: Al completar una traducción pendiente, eliminar su fila de esta tabla y commitear el cambio con mensaje `"content: add EN translation of <nombre-proyecto>"`.
