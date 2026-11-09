# ✅ Reporte de calidad de los datos

Volver a [INICIO](../INICIO.md).

- **Dataset:** Estudios incluidos en la revisión sistemática sobre gobernanza territorial de la APS (v1.0)
- **Fecha de evaluación:** 8 de noviembre de 2026

## Perfil

| Archivo | Filas | Columnas | Celdas vacías | % vacío |
|---|---|---|---|---|
| `estudios_incluidos.csv` | 20 | 13 | 18 | 6,9 % |
| `flujo_prisma.csv` | 13 | 6 | 8 | 10,3 % |

Años de publicación de los estudios incluidos: 2010–2025 (mediana 2023; 9 de 20 publicados en 2024–2025).

## Valores faltantes

| Variable | Vacíos | Explicación | Acción |
|---|---|---|---|
| `num_ref_manuscrito` / `referencia_completa` | 7 | Los estudios **E02, E05, E06, E10, E11, E13 y E18** aparecen en la Tabla 1 pero **no en la lista de referencias** del manuscrito | ⏳ **Pendiente**: completar las 7 referencias en el manuscrito y en el CSV |
| `pais_iso3` | 4 | E03, E04, E17 son multipaís; E11 es la región del Caribe | Esperado; no requiere acción |
| `motivo_exclusion` | 8 | Solo aplica a pasos de exclusión | Esperado; no requiere acción |

## Consistencia

| Verificación | Resultado |
|---|---|
| `id_estudio` único | ✅ |
| Flujo PRISMA cuadra (118 → 116 → 24 → 20) | ✅ |
| Filas de `estudios_incluidos.csv` = paso P13 (20) | ✅ |
| Conteo por herramienta de calidad = Tabla 2 del manuscrito (12 / 5 / 3) | ✅ |
| Conteo por diseño = texto de la sección 5.2 | ⚠️ **No cuadra** (ver abajo) |
| Conteo por región = texto de la sección 5.2 | ⚠️ **No cuadra** (ver abajo) |

### ⚠️ Inconsistencia 1: diseños (sección 5.2 vs. Tabla 1)

El texto dice: cualitativos/caso n = 11, análisis de política n = 4, revisiones n = 4, metodológico n = 1.
La Tabla 1 contiene: cualitativos/caso **11**, análisis de política **3** (E02, E07, E13), revisiones **5** (E09, E16, E17, E19, E20), metodológico **1**. La Tabla 2 (5 revisiones, 3 de política) coincide con la Tabla 1, así que el error está en el texto.

### ⚠️ Inconsistencia 2: distribución geográfica (sección 5.2 vs. Tabla 1)

El texto dice: África subsahariana 5, Asia 5, América Latina y Caribe 2, Oceanía 1, global/multilateral 4 (**suma 17, no 20**).
La Tabla 1 contiene: África subsahariana **6** (Sudáfrica ×2, Etiopía ×3, Nigeria), Asia **6** (China ×2, India ×2, Filipinas, Laos) + Iraq **1**, América Latina y Caribe **2**, **Canadá 1** (no mencionado en el texto ni en el resumen), Oceanía 1, global/multilateral **3**.

**Acción sugerida:** corregir la sección 5.2 y el resumen del manuscrito con los conteos de la Tabla 1 (o revisar la Tabla 1 si el error está ahí).

## Validación

- Codificación UTF-8 verificada (tildes y ñ legibles).
- Archivos validados contra el esquema de `datapackage.json` (tipos, llaves primarias y valores permitidos).

## Conclusión

El dataset es **utilizable** para describir los estudios incluidos. Antes de publicarlo de forma abierta, conviene resolver las 7 referencias faltantes y las dos inconsistencias del manuscrito.
