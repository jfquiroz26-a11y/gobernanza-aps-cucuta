# 📘 Diccionario de datos

Descripción, variable por variable, de los archivos CSV del repositorio. Volver a [INICIO](../INICIO.md).

**Formato común:** UTF-8, separador coma (`,`), primera fila = encabezados, texto con comas entre comillas dobles, celdas vacías = dato no disponible.

---

## Tabla 1: `data/processed/estudios_incluidos.csv`

**Archivo:** [estudios_incluidos.csv](../data/processed/estudios_incluidos.csv) · **Unidad:** un estudio incluido en la síntesis. **Filas:** 20. **Columnas:** 13. **Llave primaria:** `id_estudio`.

| # | Variable | Tipo | Descripción | Ejemplos | Valores válidos | Origen |
|---|---|---|---|---|---|---|
| 1 | `id_estudio` | Texto (identificador) | Identificador único del estudio, en el orden de la Tabla 1 del manuscrito | `E01`, `E14` | `E01`–`E20` | Asignado |
| 2 | `num_ref_manuscrito` | Entero | Número de la referencia en la lista de referencias del manuscrito | `29`, `4` | 1–44; vacío si el estudio no aparece en la lista | Manuscrito |
| 3 | `autores` | Texto | Autor(es) en forma abreviada, como en la Tabla 1 | `Brixi et al.` | Texto libre | Manuscrito, Tabla 1 |
| 4 | `anio` | Entero | Año de publicación | `2013`, `2025` | 2006–2026 | Manuscrito, Tabla 1 |
| 5 | `pais_region` | Texto | País, subregión o ámbito del estudio, tal como se reporta | `India (Karnataka)`, `Caribe` | Texto libre | Manuscrito, Tabla 1 |
| 6 | `pais_iso3` | Categórica | Código de país ISO 3166-1 alfa-3 | `ETH`, `BRA` | Códigos ISO3; vacío si el estudio es multipaís o regional | **Derivada** de `pais_region` |
| 7 | `region_oms` | Categórica | Región de la OMS a la que pertenece el país del estudio | `AFR`, `WPR` | `AFR` África · `AMR` Américas · `SEAR` Asia Sudoriental · `EMR` Mediterráneo Oriental · `WPR` Pacífico Occidental · `GLOBAL` multipaís/multilateral | **Derivada** de `pais_region` |
| 8 | `diseno_reportado` | Texto | Diseño metodológico tal como se reporta en la Tabla 1 | `Etnografía institucional` | Texto libre | Manuscrito, Tabla 1 |
| 9 | `categoria_diseno` | Categórica | Agrupación del diseño en cuatro categorías | `revision` | `cualitativo_caso` · `analisis_politica` · `revision` · `metodologico` | **Derivada** (ver regla abajo) |
| 10 | `herramienta_calidad` | Categórica | Instrumento de evaluación crítica aplicado según el diseño | `CASP cualitativo` | `CASP cualitativo` · `CASP revision sistematica` · `JBI politica/transversal` | **Derivada** (ver regla abajo) |
| 11 | `foco_tematico` | Texto | Foco temático principal del estudio | `Inequidades en transformación digital de APS` | Texto libre | Manuscrito, Tabla 1 |
| 12 | `en_lista_referencias` | Booleano | Indica si el estudio tiene referencia completa en el manuscrito | `true` | `true` / `false` | Verificación propia |
| 13 | `referencia_completa` | Texto | Referencia bibliográfica completa (estilo Vancouver) | — | Texto libre; vacío si `en_lista_referencias = false` | Manuscrito, sección 10 |

### Reglas de derivación

**`categoria_diseno`**
- `cualitativo_caso` ← estudios cualitativos, participativos, de implementación, etnografías y estudios de caso (único, múltiple o descriptivo), incluido el análisis temático cualitativo.
- `analisis_politica` ← análisis de política y análisis de contenido de política.
- `revision` ← revisión sistemática, de alcance o narrativa.
- `metodologico` ← estudio metodológico (solo E04).

**`herramienta_calidad`** (sección 4.7 del manuscrito)
- `cualitativo_caso` y `metodologico` → `CASP cualitativo`
- `revision` → `CASP revision sistematica`
- `analisis_politica` → `JBI politica/transversal`

Esta regla reproduce exactamente los conteos de la Tabla 2 del manuscrito (12 / 5 / 3). La asignación de E04 (metodológico) a CASP cualitativo es **inferida** de esos conteos.

---

## Tabla 2: `data/processed/flujo_prisma.csv`

**Archivo:** [flujo_prisma.csv](../data/processed/flujo_prisma.csv) · **Unidad:** un paso del diagrama de flujo PRISMA 2020. **Filas:** 13. **Columnas:** 6. **Llave primaria:** `id_paso`.

| # | Variable | Tipo | Descripción | Ejemplos | Valores válidos |
|---|---|---|---|---|---|
| 1 | `id_paso` | Texto (identificador) | Identificador del paso, en orden | `P01` | `P01`–`P13` |
| 2 | `fase` | Categórica | Fase PRISMA 2020 | `cribado` | `identificacion` · `cribado` · `elegibilidad` · `inclusion` |
| 3 | `descripcion` | Texto | Qué se cuenta en ese paso | `Reportes excluidos` | Texto libre |
| 4 | `fuente` | Categórica | Base de datos de origen | `Scopus` | `Scopus` · `PubMed` · `Scopus+PubMed` |
| 5 | `n` | Entero | Número de registros o reportes | `116` | ≥ 0 |
| 6 | `motivo_exclusion` | Texto | Motivo, solo en pasos de exclusión | `Fuera de alcance de diseño` | Texto libre; vacío si no aplica |

**Reglas de consistencia** (verificadas): P01 + P02 − P03 − P04 = P05 · P05 − P06 = P07 = P09 · P09 − (P10 + P11 + P12) = P13 = 20 = filas de `estudios_incluidos.csv`.

---

## 🔗 Relación entre tablas

No hay llave común: `flujo_prisma.csv` es un resumen agregado del proceso y `estudios_incluidos.csv` detalla el resultado final (paso `P13`).
