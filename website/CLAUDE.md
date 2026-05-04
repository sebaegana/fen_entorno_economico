# Entorno Económico — Quarto Website

Sitio web docente construido con Quarto para el curso "Entorno Económico y
Financiero para las Decisiones de Inversión" (FEN, Universidad de Chile).

## Estructura del proyecto

```
website/
├── _quarto.yml          # configuración global del sitio
├── index.qmd            # página de inicio
├── about.qmd
├── recursos.qmd
├── contacto.qmd
├── styles.css           # estilos globales (paleta teal #0d6e6e)
└── clases/
    ├── index.qmd                        # índice de clases
    ├── styles.html                      # estilos para slides revealjs
    ├── claseXX_diapositiva.qmd          # slides de la clase
    ├── claseXX_actividad_[nombre].qmd   # actividades (una o más, en orden de la sesión)
    ├── claseXX_notas_docente.qmd        # notas de apoyo docente
    ├── claseXX_plan_mejora.qmd          # reflexión post-clase
    ├── imagenes/        # imágenes usadas en slides y actividades
    ├── materiales/      # PDFs, PPTX y ZIPs de apoyo
    └── data/            # archivos Excel de ejercicios
```

## Comandos clave

```bash
# Renderizar todo el sitio
quarto render

# Previsualizar con live reload
quarto preview

# Renderizar solo un archivo
quarto render clases/diapositiva_01.qmd
```

Ejecutar desde la carpeta `website/`. El output va a `docs/`.

## Convenciones de archivos

Todos los archivos de una clase usan el prefijo `claseXX_` (ej. `clase01_`).

**Cadencia dentro de cada clase** (orden de la sesión):
1. `claseXX_diapositiva.qmd` — slides principales, siempre este nombre exacto
2. `claseXX_actividad_NN_[nombre].qmd` — una o más actividades; `NN` es el número de orden en la sesión (01, 02…); `[nombre]` describe el contenido (ej. `apertura`, `pib`, `ipc`)
3. `claseXX_notas_docente.qmd` — material de apoyo docente, siempre este nombre exacto
4. `claseXX_plan_mejora.qmd` — reflexión post-clase, siempre este nombre exacto

**Referencias entre archivos:** nunca incluir la extensión `.qmd` en los links ni en las menciones inline. Usar solo el nombre base (ej. `clase01_actividad_02_pib`, no `clase01_actividad_02_pib.qmd`).

**Otros recursos:**
- Imágenes referenciadas en QMDs: `imagenes/nombre_descriptivo.png`
- Materiales originales (PPTX, PDF fuente): `materiales/`, no se referencian en QMD
- Datos para ejercicios: `data/ejercicio XX nombre.xlsx`

## Convenciones de slides (revealjs)

- Separador de slides: `------------------------------------------------------------------------`
- Sección nueva (título grande): `# Nombre sección`
- Slide normal: `## Título del slide`
- Fórmulas: LaTeX inline `$...$` o display `$$...$$`
- Imágenes: `![](imagenes/nombre.png){fig-align="center" width="75%"}`
- El logo siempre apunta a `imagenes/Imagen1.jpg`
- `incremental: false` — listas aparecen completas por defecto

## Convenciones de contenido

- Idioma: español (lang: es)
- Pie de página slides: `© Sebastián Egaña Santibáñez — Entorno Económico`
- Tema base: `cosmo` (HTML) y `simple` (revealjs)
- Colores CSS: acento `#0d6e6e`, fondo suave `#e7f4f4`, texto `#1d2a33`

## Cuando se agrega una clase nueva

1. Crear `clases/claseXX_diapositiva.qmd` con el YAML de `clase01_diapositiva.qmd` como base
2. Crear `clases/claseXX_actividad_[nombre].qmd` por cada actividad de la sesión
3. Crear `clases/claseXX_notas_docente.qmd` y `clases/claseXX_plan_mejora.qmd`
4. Copiar imágenes nuevas a `clases/imagenes/`
5. Copiar materiales originales a `clases/materiales/`
6. Copiar archivos de datos a `clases/data/`
7. Actualizar `clases/index.qmd` con el enlace a la nueva clase

## Formato de casos (cases/)

Los casos son documentos PDF independientes (no páginas web). Estructura de archivos en `cases/YYYYMM_caseXX/`:

- `case01.qmd` — único archivo que renderiza enunciado y pauta
- `_quarto.yml` — define el perfil `pauta`

**Formato** (HTML standalone + PDF con logo y footer — equivalente al notebook de clases, no es parte del sitio web):
```yaml
format:
  html:
    theme: cosmo
    self-contained: true
    toc: true
    toc-title: "Contenido"
  pdf:
    toc: false
    papersize: a4
    geometry: "top=1.5in, bottom=1in, left=1in, right=1in"
    include-in-header:
      text: |
        \usepackage{fancyhdr}
        \usepackage{graphicx}
        \usepackage{transparent}
        \usepackage{mdframed}
        \pagestyle{fancy}
        \fancyhf{}
        \lhead{\center{\transparent{0.4}\includegraphics[width=14cm]{../../website/clases/imagenes/Imagen1.jpg}}}
        \rfoot{Página \thepage}
        \cfoot{© Sebastián Egaña Santibáñez --- Entorno Económico}
        \renewcommand{\headrulewidth}{0pt}
        \renewcommand{\footrulewidth}{0pt}
```

**Toggle enunciado/pauta** — usar Quarto profiles:
```
::: {.content-visible when-profile="pauta"}
::: {.callout-note appearance="simple" title="Respuesta"}
Contenido de la respuesta
:::
:::
```

Renderizar:
- `quarto render case01.qmd` → enunciado
- `quarto render case01.qmd --profile pauta` → pauta

## Fuente original

Las clases se trabajan a partir de presentaciones PPTX. Para extraer el
contenido de un PPTX nuevo, renombrarlo como .zip y descomprimir; el texto
está en `ppt/slides/slideN.xml` y las imágenes en `ppt/media/`.
