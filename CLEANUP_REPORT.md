# Reporte de Auditoría y Limpieza — Fase 1 (CV Juan Hernández)

## 1. Resumen

Se completó exitosamente la **Fase 1: Limpieza e Inventario Inicial** del repositorio del CV personal de Juan Hernández.

La limpieza se realizó con un criterio **conservador**: no se alteró el diseño visual, no se modificaron estilos CSS, no se reestructuró la arquitectura de Hugo ni se alteró el contenido profesional del CV.

### Resultados Cuantitativos Principales

| Métrica | Estado Inicial (Antes) | Estado Final (Después) | Diferencia / Impacto |
| :--- | :--- | :--- | :--- |
| **Archivos totales en disco** (excl. `.git`) | 1,707 archivos | 43 archivos fuente + artefactos ignorados | **-1,664 archivos** eliminados/ignorados |
| **Archivos fuente en repositorio** | 103 archivos | 43 archivos | **-60 archivos** no pertenecientes al CV |
| **Tamaño total de archivos fuente** | ~11.3 MB | 4.90 MB | **-6.4 MB (-56.6%)** reducidos |
| **Espacio total ahorrado en el repo** | ~88 MB (con `public`, `node_modules`, `resources`) | 4.90 MB | **~83 MB ahorrados** |
| **Páginas compiladas por Hugo (EN / ES)** | 95 EN / 57 ES | 45 EN / 52 ES | Removido contenido de plantilla/blog de prueba |
| **Resultado de `hugo --minify`** | **ERROR** (`preact` missing) | **ÉXITO** (Compilación limpia en 4.3s) | Sitio 100% funcional |
| **Resultado de `npm ci`** | Audited 32 packages | Audited 33 packages (0 vulnerabilities) | Instalación limpia sincronizada |

---

## 2. Archivos y Directorios Eliminados (por Categoría)

### A. Proyectos Ajenos / Aplicaciones Independientes
- `DaniOS/` (33 archivos): Aplicación independiente en Streamlit/Python para administración financiera personal y de activos. Se confirmó que no posee ninguna integración o referencia desde Hugo, GitHub Actions ni el `README.md`.

### B. Artefactos Generados e Ignorados
- `node_modules/` (19.59 MB): Dependencias de Node. Se eliminó del control de versiones y se configuró en `.gitignore`.
- `public/` (43.63 MB): Directorio de salida del build de Hugo. Eliminado del versionado y agregado a `.gitignore`.
- `resources/_gen/` (13.29 MB): Caché interna de procesamiento de imágenes de Hugo. Eliminado del versionado y agregado a `.gitignore`.
- `.hugo_build.lock`: Archivo de bloqueo temporal creado durante builds de Hugo. Agregado a `.gitignore`.
- `hugo_stats.json` (13.7 KB): Archivo de estadísticas generado dinámicamente por Hugo cuando `writeStats: true` está habilitado. Se confirmó que Hugo lo regenera automáticamente en cada build sin ser necesario como fuente versionada; se eliminó y agregó a `.gitignore`.
- `logs/` (`xvba_debug.log`): Log local del IDE de desarrollo. Eliminado y agregado a `.gitignore`.

### C. Contenido de Demostración / Plantilla (Hugo Blox Template)
- `content/en/project/pandas/` (`index.md`, `featured.png`, `featured2.png` - 1.55 MB): Proyecto de demostración sobre Pandas/Data Science.
- `content/en/project/pytorch/` (`index.md`, `featured.png`, `featured2.png` - 1.75 MB): Proyecto de demostración sobre PyTorch/Deep Learning.
- `content/en/project/scikit/` (`index.md`, `featured.png`, `featured2.png` - 1.66 MB): Proyecto de demostración sobre Scikit-Learn.
- `content/en/project/tech/` (8 archivos Markdown/YAML): Colección de artículos de prueba para un blog técnico de ejemplo ("About Tech Blog.md", "First Steps with Go.md", "Git Setup on Ubuntu.md", "HTML Page Basics.md", "JavaScript Function Example.md", "Menus.yaml for Tech Blog Navigation.yaml", "NumPy Array Basics.md", "Tech Blog Homepage.md").
- `content/es/nuevo_analisis.md` (326 bytes): Borrador Markdown de pruebas con título de prueba `"gadfgdfgdfsgsfhshs"`.

### D. Archivos Temporales y Documentos Duplicados de la Raíz
- `Juan Hernandez (CV-2026).pdf` (155 KB): Copia redundante ubicada en la raíz. El sitio web utiliza y enlaza formalmente a `static/uploads/resume.pdf`.
- `cv_text.txt` (2.5 KB): Volcado de texto extraído del PDF que no intervenía en el build.
- `read_pdf.py` (376 bytes): Script Python temporal utilizado para la extracción de texto del PDF.

### E. Assets de Imagen Secundarios / No Utilizados
- `content/en/authors/admin/avatar2.png` (302 KB): Imagen estática secundaria no referenciada.
- `content/en/authors/admin/avatar_animated.png` (708 KB): Versión animada no referenciada.
- `content/es/authors/admin/avatar2.png` (708 KB): Imagen estática secundaria no referenciada en la sección en español.

### F. Workflows y Metadatos Heredados de GitHub
- `.github/workflows/import-publications.yml`: Workflow para conversión de archivos BibTeX (`publications.bib`). Innecesario al no existir publicaciones académicas en formato BibTeX.
- `.github/workflows/updater-wip.yml`: Action orientada a la actualización del feed de HugoBlox.
- `.github/FUNDING.yml`: Configuración de patrocinio apuntando al autor de la plantilla (`gcushen`).

---

## 3. Archivos Conservados

### Estructura de Contenido Profesional
- **English Content (`content/en/`)**:
  - `_index.md`: Configuración de la página principal / Landing.
  - `experience.md`: Historial laboral y académico.
  - `projects.md`: Galería y listado de proyectos.
  - `skills.md`: Habilidades técnicas, herramientas e idiomas.
  - `authors/_index.md` & `authors/admin/_index.md`: Perfil profesional de Juan Hernández.
  - `project/bioinformatics-analyzer.md`: Proyecto real "AU480 QC Data Automation".
  - `project/clinical-data-pipeline.md`: Proyecto real "Excel/CSV Laboratory Data Automation".
  - `project/lab-dashboard.md`: Proyecto real "Clinical KPI Dashboard".

- **Español Content (`content/es/`)**:
  - `_index.md`: Configuración de la página principal en español.
  - `experience.md`: Experiencia y Educación en español.
  - `projects.md`: Proyectos en español.
  - `skills.md`: Habilidades e Idiomas en español.
  - `authors/_index.md` & `authors/admin/_index.md`: Perfil profesional de Juan Hernández en español.
  - `project/bioinformatics-analyzer.md`: Proyecto real en español.
  - `project/clinical-data-pipeline.md`: Proyecto real en español.
  - `project/lab-dashboard.md`: Proyecto real en español.
  - `project/laboratory-report-consolidation.md`: Proyecto real en español "Herramienta de Consolidación de Reportes de Laboratorio".

### Configuración del Sitio (`config/_default/`)
- `hugo.yaml`: Configuración principal de Hugo (writeStats, permalinks, build).
- `languages.yaml`: Configuración bilingüe (EN predeterminado / ES secundario).
- `menus.en.yaml` & `menus.es.yaml`: Estructura de navegación para cada idioma.
- `module.yaml`: Configuración de montajes de Hugo Modules / Blox.
- `params.yaml`: Metadatos SEO, nombre de la persona, copyright y características.

### Assets y Layouts Personalizados
- `static/uploads/resume.pdf` (41 KB): PDF oficial del CV descargable desde la web.
- `assets/css/custom.css`: Estilos CSS personalizados conservados íntegramente.
- `assets/jsconfig.json`: Mapeo de rutas JS para Hugo Blox.
- `assets/media/icons/.gitkeep`: Mantenedor de estructura para iconos de medios.
- `layouts/partials/hooks/head-end/github-button.html`: Inyección de script para botones de GitHub en la cabecera.

---

## 4. Dependencias y Diagnóstico de `preact`

### Diagnóstico Técnico Obligatorio

1. **Error Original**:
   Al ejecutar la compilación de producción con Hugo, el comando fallaba con el siguiente mensaje de error de `esbuild` / `JSBUILD`:
   ```text
   ERROR js.Build failed: ".../modules/blox-tailwind@v0.10.0/blox/hero/client.jsx:21:15": Could not resolve "preact/jsx-runtime"
   ERROR js.Build failed: ".../modules/blox-tailwind@v0.10.0/blox/shared/js/components/Icon.jsx:2:16": Could not resolve "preact"
   ```

2. **Comando para Reproducirlo**:
   ```bash
   hugo --minify
   ```

3. **Causa y Solución**:
   El módulo de temas `github.com/HugoBlox/hugo-blox-builder/modules/blox-tailwind@v0.10.0` contiene componentes interactivos escritos en JSX (`hero/client.jsx`, `hero/component.jsx`, `Icon.jsx`) que importan explícitamente `preact` y `preact/jsx-runtime`.
   Durante la generación del sitio, Hugo invoca a `esbuild` para empaquetar dichos archivos JSX. `esbuild` busca el módulo `preact` dentro de la carpeta `node_modules` del proyecto.
   Al declarar `"preact": "^10.29.8"` dentro de `package.json`, la dependencia queda formalizada en el proyecto y disponible tanto para builds locales como para el pipeline de GitHub Actions (`npm ci`).

4. **Versión Instalada**:
   `preact`: `^10.29.8` (en `package.json` y fijada en `package-lock.json`).

5. **Sincronización y Validación (`npm ci`)**:
   Se ejecutó `npm install` seguido de `npm ci`. El comando `npm ci` confirmó una instalación limpia y 100% sincronizada entre `package.json` y `package-lock.json`:
   ```text
   added 32 packages, and audited 33 packages in 5s
   found 0 vulnerabilities
   ```

6. **Resultado Posterior de `hugo --minify`**:
   Compilación limpia y sin errores de transformación de JavaScript:
   ```text
                     │ EN │ ES 
   ──────────────────┼────┼────
    Pages            │ 45 │ 52 
    Paginator pages  │  0 │  0 
    Non-page files   │  1 │  1 
    Static files     │  1 │  1 
    Processed images │  9 │  6 
    Aliases          │ 13 │ 16 

   Total in 4309 ms
   ```

---

## 5. Workflows de CI/CD

- **Workflow Conservado**:
  - `.github/workflows/publish.yaml`: Es el pipeline activo de GitHub Actions para el despliegue del CV en **GitHub Pages**. Ejecuta `actions/checkout@v4`, `peaceiris/actions-hugo@v3` (Hugo extended 0.161.1), `actions/setup-node@v4` (Node 22), `npm ci`, `hugo --minify` y `pagefind` indexer.

- **Workflows Eliminados**:
  - `.github/workflows/import-publications.yml` (Heredado de plantilla academic/bibtex).
  - `.github/workflows/updater-wip.yml` (Heredado del org HugoBlox).

---

## 6. Assets y Documentos Utilizados

- **Fotografía de Perfil (Avatar Oficial)**:
  - `content/en/authors/admin/avatar.png` (2.44 MB)
  - `content/es/authors/admin/avatar.png` (2.44 MB)
  *(Ambos corresponden a la imagen oficial utilizada por el bloque de biografía de Hugo Blox)*.

- **Documento PDF del CV**:
  - `static/uploads/resume.pdf` (40.9 KB)
  *(Enlazado en los botones de descarga de `content/en/_index.md` y `content/es/_index.md`)*.

---

## 7. Evaluación de Riesgos

- **Riesgo de eliminaciones**: **NULO**. Todas las eliminaciones correspondieron a archivos de ejemplo, artefactos regenerables dinámicamente o código ajeno (`DaniOS`).
- **Verificación de referencias**: Se realizaron búsquedas exactas con `ripgrep` de cada archivo eliminado para asegurar que no existieran enlaces rotos en los Markdown o configuraciones YAML/TOML del CV.

---

## 8. Validación y Comandos

1. **Prueba de Instalación CI**:
   ```bash
   npm ci
   ```
   *Resultado*: Éxito. 33 paquetes auditados en 5s.

2. **Prueba de Compilación Hugo**:
   ```bash
   hugo --minify
   ```
   *Resultado*: Éxito. Generación completa de 97 páginas (45 EN + 52 ES) en 4.3 segundos con código de salida `0`.

---

## 9. Estado Final

```text
PHASE 1 CLEANUP: COMPLETE
```
