# ✅ Reporte de calidad de los datos

Volver al [índice](../INICIO.md).

- **Dataset:** Estudios incluidos en la revisión sistemática sobre gobernanza territorial de la APS (v1.0.0)
- **Fecha de evaluación:** 9 de noviembre de 2026

## Perfil

| Archivo | Filas | Columnas | Celdas vacías | % vacío |
|---|---|---|---|---|
| `estudios_incluidos.csv` | 20 | 13 | 11 | 4,2 % |
| `flujo_prisma.csv` | 13 | 6 | 8 | 10,3 % |

Años de publicación de los estudios incluidos: 2010–2025 (mediana 2023; 9 de 20 publicados en 2024–2025).

### Distribución de los estudios

| Categoría de diseño | n | | Región OMS | n | | Herramienta de calidad | n |
|---|---|---|---|---|---|---|---|
| `cualitativo_caso` | 11 | | `AFR` | 6 | | CASP cualitativo | 12 |
| `revision` | 5 | | `WPR` | 5 | | CASP revisión sistemática | 5 |
| `analisis_politica` | 3 | | `AMR` | 3 | | JBI política/transversal | 3 |
| `metodologico` | 1 | | `GLOBAL` | 3 | | | |
| | | | `SEAR` | 2 | | | |
| | | | `EMR` | 1 | | | |

## Valores faltantes

Todos los valores vacíos son esperados por diseño:

| Variable | Vacíos | Explicación |
|---|---|---|
| `num_ref_manuscrito` | 7 | Los estudios E02, E05, E06, E10, E11, E13 y E18 no tienen número en la lista de referencias del manuscrito; su referencia completa se obtuvo de la publicación original (`en_lista_referencias = false`) |
| `pais_iso3` | 4 | E03, E04 y E17 son multipaís; E11 corresponde a la región del Caribe |
| `motivo_exclusion` | 8 | Solo aplica a los pasos de exclusión |

## Consistencia

| Verificación | Resultado |
|---|---|
| `id_estudio` único | ✅ |
| Flujo PRISMA consistente (118 → 116 → 24 → 20) | ✅ |
| Filas de `estudios_incluidos.csv` = paso P13 (20) | ✅ |
| Conteo por herramienta de calidad = síntesis de calidad del manuscrito (12 / 5 / 3) | ✅ |
| 20 de 20 estudios con referencia completa y DOI o datos de publicación | ✅ |

### Notas de procedencia

- Los conteos por diseño y región de este dataset se calculan estudio por estudio a partir de la tabla de características del manuscrito (versión del 11-05-2026). Pueden diferir de los conteos agregados reportados en el texto de esa versión preliminar.
- La autoría abreviada de E18 se registra como **Haenssgen et al.**, conforme a la publicación original (BMJ Global Health, 2024).

## Validación

- Codificación UTF-8 verificada.
- Ambos CSV validados con Frictionless Framework contra el esquema de `datapackage.json` (tipos de datos, llaves primarias, valores permitidos): **VALID**.
- `CITATION.cff` validado contra el esquema CFF 1.2.0; `metadata/dcat.ttl` y `metadata/schemaorg.jsonld` verificados sintácticamente.

## Conclusión

El dataset es apto para describir y reanalizar las características de los estudios incluidos en la revisión.
