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
2. `claseXX_actividad_[nombre].qmd` — una o más actividades; `[nombre]` describe el contenido (ej. `apertura`, `pib`, `ipc`); el orden alfabético de `[nombre]` no importa, el orden real es el que se usa en la sesión
3. `claseXX_notas_docente.qmd` — material de apoyo docente, siempre este nombre exacto
4. `claseXX_plan_mejora.qmd` — reflexión post-clase, siempre este nombre exacto

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

## Fuente original

Las clases se trabajan a partir de presentaciones PPTX. Para extraer el
contenido de un PPTX nuevo, renombrarlo como .zip y descomprimir; el texto
está en `ppt/slides/slideN.xml` y las imágenes en `ppt/media/`.
