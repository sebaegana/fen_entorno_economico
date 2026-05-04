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
    ├── index.qmd        # índice de clases
    ├── styles.html      # estilos para slides revealjs
    ├── diapositiva_XX.qmd   # slides de cada clase
    ├── notebook_XX.qmd      # notebooks en formato PDF
    ├── imagenes/        # imágenes usadas en slides y notebooks
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

- Diapositivas: `diapositiva_XX.qmd` — formato `revealjs` + `pdf`
- Notebooks: `notebook_XX.qmd` — formato `pdf`
- Imágenes referenciadas en slides: `imagenes/nombre_descriptivo.png`
- Materiales originales (PPTX, PDF fuente): van en `materiales/`, no se
  referencian directamente en el QMD
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

1. Crear `clases/diapositiva_XX.qmd` con el YAML de la diapositiva_01 como base
2. Copiar imágenes nuevas a `clases/imagenes/`
3. Copiar materiales originales a `clases/materiales/`
4. Copiar archivos de datos a `clases/data/`
5. Actualizar `clases/index.qmd` con el enlace a la nueva diapositiva

## Fuente original

Las clases se trabajan a partir de presentaciones PPTX. Para extraer el
contenido de un PPTX nuevo, renombrarlo como .zip y descomprimir; el texto
está en `ppt/slides/slideN.xml` y las imágenes en `ppt/media/`.
