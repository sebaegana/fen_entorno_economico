# Contexto de sesión — 27 de abril de 2026

## Qué se construyó en esta sesión

Partimos de una carpeta con materiales dispersos de la Clase 01 del curso "Entorno Económico y Financiero para las Decisiones de Inversión" (FEN, Universidad de Chile) y construimos un sitio web Quarto completo con materiales docentes estructurados.

---

## Estructura final del proyecto

```
website/
├── CLAUDE.md                        ← configuración del proyecto para Claude Code
├── _quarto.yml                      ← configuración Quarto (output: docs/)
├── index.qmd                        ← página de inicio
├── about.qmd
├── recursos.qmd                     ← fuentes para economía (INE, BCCh, OCDE, etc.)
├── contacto.qmd
├── styles.css                       ← paleta teal (#0d6e6e)
├── .gitignore / .editorconfig
└── clases/
    ├── index.qmd                    ← índice de la clase 01
    ├── styles.html                  ← estilos revealjs
    ├── clase01_diapositiva.qmd      ← slides reformulados (42 slides, ~75 min)
    ├── clase01_notebook.qmd         ← notebook de R (Finanzas en R)
    ├── clase01_actividad_apertura.qmd
    ├── clase01_actividad_pib.qmd
    ├── clase01_actividad_ipc.qmd
    ├── clase01_actividad_coyuntura.qmd
    ├── clase01_notas_docente.qmd
    ├── clase01_plan_mejora.qmd
    ├── imagenes/
    │   ├── Imagen1.jpg
    │   ├── mercado_laboral_clasificacion.png
    │   ├── desempleo_estres_scatter.jpeg
    │   ├── clp_historico.png
    │   └── tcr_historico.png
    ├── materiales/
    │   ├── clase_01_202509.pdf
    │   ├── clase_01_202509.pptx
    │   ├── INE_empleo_01.pdf
    │   └── ejercicios clase 01.zip
    └── data/
        ├── ejercicio 01 PIB.xlsx
        ├── ejercicio 02 IPC.xlsx
        └── ejercicio 03 Salario.xlsx
```

---

## Decisiones de diseño

### Sitio web
- Basado en el sitio de referencia: `C:\Users\sebae\Downloads\FEN - LLM e IA\iaglto_clases_website`
- Tema: cosmo (HTML) + simple (revealjs)
- Colores: acento `#0d6e6e`, suave `#e7f4f4`, texto `#1d2a33`
- Output en `docs/` (compatible con GitHub Pages)

### Estructura de archivos
- Prefijo `clase01_` en todos los archivos de la primera clase
- Subcarpetas `imagenes/`, `materiales/`, `data/` dentro de `clases/`
- Las actividades son archivos independientes, no embebidas en la diapositiva

### Diapositiva reformulada
- **Hilo conductor:** titular CNN del 10 abr 2026 (*"US inflation tripled..."*) abre y cierra la clase
- **Nuevo bloque:** Situación Fiscal de Chile con datos reales del CFA e IPoM
- **Datos reales integrados:** IPoM marzo 2026 y CFA 4T25 en múltiples slides
- **Duración estimada:** ~75 min contenido solo; ~85 min con actividad apertura

---

## Actividades desarrolladas

### 1. Apertura — ¿Qué nos dice este titular? (~10 min)
- Titular: *"US inflation tripled last month on record spike in gas prices"* — CNN Business, 10 abr. 2026
- IPC marzo 2026: +0,9% mensual / +3,3% anual; gasolina +21,2%
- 3 preguntas: qué mide, a quién afecta, qué necesitan saber
- Cierre: "para llevar" que cierra el círculo al final de la clase

### 2. PIB — ¿Cuenta o no cuenta? (~15 min)
- 8 casos: almuerzo en casa, cobre a China, carretera MOP, taxista informal, compra de acciones, chileno en Argentina, WhatsApp, pensión AFP
- Ordered de menor a mayor dificultad
- Enseña: producción vs. transferencia, PIB vs. PNB, medición vs. definición, economía digital

### 3. IPC — Construyamos un índice (~18 min)
- Canasta de 5 bienes, base exacta $100.000 → IPC = 118, inflación = 18%
- Bencina sube 50% → explica 10 de los 18 pp (conecta con titular apertura)
- 3 partes: canasta propia, cálculo con la canasta del curso, inflación personal vs. oficial
- Laspeyres paso a paso con números limpios

### 4. Coyuntura — ¿Chile está en quiebra? (~25 min)
- Basada en debate político real de marzo 2026 (FastCheck: #Falso)
- 3 bloques: actividad/precios (IPoM), fiscal (CFA), riesgo soberano
- Distinción central: **estrés fiscal** ≠ **default/quiebra**
- Citas textuales del CFA con número de página
- Pregunta de integración: ¿qué harían como asesores del nuevo gobierno?

---

## Documentos fuente utilizados

| Documento | Uso |
|---|---|
| `IPoM marzo 2026.pdf` (BCCh) | Datos macro: PIB, inflación, proyecciones |
| `Informe sobre desvío de la meta de BE de 2025 - 04.03.2026.pdf` (CFA) | BE -3,6%, desvíos, activos Tesoro |
| `Informe de Balance Estructural y Nivel Prudente de Deuda 4T25.pdf` (CFA) | Deuda, proyecciones 2026-2030, riesgo |
| `clase_01_202509.pptx` | Fuente original de la diapositiva (41 slides extraídos) |
| CNN Business, 10 abr. 2026 | Titular para actividad apertura y coyuntura |
| FastCheck.cl, El Dínamo, BioBioChile, 25 mar. 2026 | Verificación afirmación "quiebra" |

---

## Datos clave de Chile 2026

### Macro (IPoM marzo 2026)
- PIB 2025: +2,5% real
- PIB 2026 proyectado: 1,5–2,5%
- Inflación feb. 2026: 2,4% anual (bajo la meta de 3%)
- Inflación proyectada Q2 2026: ~4% (shock petróleo por guerra en Medio Oriente)
- Precio petróleo: ~US$100/barril Q2 2026 (+60% vs. diciembre)
- Precio cobre: US$5,4/lb promedio 2026

### Fiscal (CFA, marzo 2026)
- Balance Estructural 2025: -3,6% del PIB (meta original: -1,1%)
- Desvío: 2,5 pp del PIB (US$8.863 millones)
- Tercer incumplimiento consecutivo sin crisis
- Deuda bruta: 41,7% del PIB (nivel prudente: 45%)
- Probabilidad de superar nivel prudente hacia 2027: ~50%
- Activos Tesoro: de US$2.946M (Q2 2025) a US$46M (cierre 2025)
- Gasto en intereses: 0,66% PIB (2015) → 1,24% PIB (2025)
- Deuda: de 3,9% PIB (2007) a 41,7% (2024) → ×10 en 17 años

### Riesgo soberano
- Clasificación Fitch: A− con perspectiva estable
- CDS 5 años: bajos, similares a 2018
- Probabilidad de default: prácticamente nula

---

## Notas al docente

El archivo `clase01_notas_docente.qmd` cubre:
- Actividad apertura: respuestas esperadas a las 3 preguntas, el error del "tripled"
- Actividad PIB: casos que generan más debate (taxista informal, WhatsApp, chileno en Argentina)
- Actividad IPC: cómo guiar cada paso, la discusión de inflación personal vs. oficial
- Actividad coyuntura: respuestas esperadas por bloque, la distinción estrés vs. quiebra
- Bloques conceptuales: puntos clave, errores frecuentes, preguntas para activar discusión

---

## Pendiente (plan de mejora)

Actividades implementadas: apertura ✅, PIB ✅, IPC ✅, coyuntura ✅

Actividades pendientes del plan:
- Actividad Imacec — lectura de datos reales (~10 min)
- Actividad mercado laboral — clasifica el caso (~15 min)  
- Actividad tipo de cambio — importador vs. exportador (~15 min)

---

## Comando para renderizar

```bash
# Desde C:\Users\sebae\Downloads\FEN - Entorno Económico\website\
quarto render
quarto preview
```
