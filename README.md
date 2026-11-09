# 📊 Estudios incluidos en la revisión sistemática sobre gobernanza territorial de la APS y determinación social de inequidades en salud (2006–2026)

![Licencia: CC BY 4.0](https://img.shields.io/badge/Licencia-CC--BY--4.0-lightgrey.svg)
![FAIR](https://img.shields.io/badge/FAIR-en%20progreso-4db8ff)
![Estado](https://img.shields.io/badge/estado-borrador%20v1.0-orange)

## 🧭 Propósito

Este repositorio contiene el **dataset de la revisión sistemática** que fundamenta la tesis doctoral *"Gobernanza territorial de la Atención Primaria en Salud y determinación social de inequidades en salud: construcción y aplicación de un marco analítico-interpretativo en Cúcuta–Norte de Santander, Colombia"*.

Su objetivo es que **otra persona investigadora pueda entender, verificar y reutilizar los datos de la revisión sin tener que preguntarle al autor**: qué estudios se incluyeron, de dónde vienen, cómo se seleccionaron y con qué criterios se clasificaron.

## 🌱 Origen

- **Fuentes:** búsquedas en **Scopus** y **PubMed** realizadas el **10 de mayo de 2026**.
- **Método:** revisión sistemática reportada según **PRISMA 2020**, pregunta estructurada con **SPIDER**, calidad evaluada con **CASP** y **JBI**, síntesis temática de **Thomas y Harden (2008)**.
- **Construcción del dataset:** las variables se compilaron a partir de la matriz de extracción y del manuscrito *Revision_Sistematica_Gobernanza_APS_Cucuta.docx* (mayo 2026). Ver [Metodología](docs/methodology.md).

## 🗺️ Alcance

| Dimensión | Cobertura |
|---|---|
| Unidad de análisis | Estudio publicado (1 fila = 1 estudio incluido) |
| Número de registros | 20 estudios incluidos · 13 pasos del flujo PRISMA |
| Periodo de publicación | 1 ene 2006 – 10 may 2026 (estudios incluidos: 2010–2025) |
| Cobertura geográfica | 11 países + la región del Caribe + 3 estudios globales/multilaterales |
| Idiomas admitidos | Español, inglés, portugués |
| Tema | Gobernanza territorial de la APS × equidad / determinación social de la salud |

## ⚠️ Límites

- **Solo dos bases de datos** (Scopus y PubMed): pueden faltar estudios indexados en LILACS, SciELO o literatura gris.
- **Sin registro previo en PROSPERO.**
- **Ningún estudio incluido es sobre Colombia**: el dataset describe evidencia internacional, no el contexto de Cúcuta.
- **No contiene los 118 registros originales** de la búsqueda ni los textos completos; solo los 20 estudios incluidos y el conteo agregado del flujo. Los exportes originales deben ubicarse en `data/raw/` (ver [instrucciones](data/raw/README.md)).
- **7 de los 20 estudios no tienen referencia completa** en el manuscrito actual (ver [Reporte de calidad](docs/quality_report.md)).
- Algunas variables son **derivadas** (región OMS, categoría de diseño, herramienta de calidad); la regla de derivación está en el [Diccionario de datos](docs/data_dictionary.md).

---

## 📁 Estructura

```
📦 Repositorio_Datos_Tesis_APS_Cucuta/
├── INICIO.md                         # Página de inicio en Obsidian
├── README.md                         # Este archivo: propósito, origen, alcance, límites
├── LICENSE                           # Condiciones de reutilización (CC BY 4.0)
├── CHANGELOG.md                      # Historial de versiones
├── CITATION.cff                      # Cómo citar el dataset (explorar)
├── datapackage.json                  # Metadatos estructurados Frictionless (explorar)
├── data/
│   ├── raw/                          # Exportes originales de Scopus/PubMed (por agregar)
│   └── processed/
│       ├── estudios_incluidos.csv    # ★ Dataset principal (20 estudios)
│       └── flujo_prisma.csv          # Flujo de selección PRISMA 2020
├── docs/
│   ├── README.md                     # Libro de códigos (codebook) + vista previa
│   ├── data_dictionary.md            # Diccionario de datos, variable por variable
│   ├── methodology.md                # Cómo se generaron los datos
│   ├── quality_report.md             # Verificaciones de calidad e inconsistencias
│   ├── ethical_considerations.md     # Aspectos éticos y derechos sobre los datos
│   └── figuras/Figura1_PRISMA_2020_flow.png
├── metadata/                         # Metadatos legibles por máquina (explorar)
│   ├── schemaorg.jsonld
│   └── dcat.ttl
└── fair/README.md                    # Declaración FAIR (explorar)
```

## 📂 Archivos clave

- `data/processed/estudios_incluidos.csv` — el dataset. Se abre en Excel, R, Python, SPSS o cualquier hoja de cálculo (UTF-8, separado por comas).
- [Diccionario de datos](docs/data_dictionary.md) — qué significa cada columna y qué valores admite.
- [Metodología](docs/methodology.md) — búsqueda, criterios, selección, extracción.
- [Reporte de calidad](docs/quality_report.md) — completitud, consistencia y pendientes.

## 🔍 Uso

1. Abre `data/processed/estudios_incluidos.csv` con tu herramienta preferida (en Excel: *Datos → Desde texto/CSV → Origen: UTF-8*).
2. Consulta el [diccionario](docs/data_dictionary.md) antes de analizar.
3. Para unir con el flujo PRISMA no hay llave común: `flujo_prisma.csv` es un resumen agregado; su paso `P13` (n = 20) corresponde al total de filas de `estudios_incluidos.csv`.

## 🧬 Declaración FAIR

Ver [fair/README.md](fair/README.md). Estado actual: **parcialmente FAIR** (formatos abiertos, documentación y licencia listas; falta DOI y depósito público).

## 📖 Cita

> Quiroz Ortega, J. F. (2026). *Estudios incluidos en la revisión sistemática sobre gobernanza territorial de la APS y determinación social de inequidades en salud (2006–2026)* (Versión 1.0) [Conjunto de datos].

Ver `CITATION.cff` para el formato estructurado.

## 📜 Licencia

Datos y documentación bajo **Creative Commons Atribución 4.0 Internacional (CC BY 4.0)**. Ver `LICENSE` y [consideraciones éticas](docs/ethical_considerations.md) para la verificación de derechos sobre los datos.

## 📬 Contacto

**Jose Fred Quiroz Ortega** — Doctorado en Salud Pública, Universidad de Pamplona  
ORCID: [orcid.org/0000-0002-1741-6067](https://orcid.org/0000-0002-1741-6067) · jfquiroz26@gmail.com
