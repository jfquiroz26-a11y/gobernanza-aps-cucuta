# 📊 Estudios incluidos en la revisión sistemática sobre gobernanza territorial de la APS y determinación social de inequidades en salud (2006–2026)

![Licencia: CC BY 4.0](https://img.shields.io/badge/Licencia-CC--BY--4.0-lightgrey.svg)
![Versión](https://img.shields.io/badge/versión-1.0.0-blue)

## 🧭 Propósito

Este repositorio contiene el **dataset de la revisión sistemática** que fundamenta la tesis doctoral *"Gobernanza territorial de la Atención Primaria en Salud y determinación social de inequidades en salud: construcción y aplicación de un marco analítico-interpretativo en Cúcuta–Norte de Santander, Colombia"* (Doctorado en Salud Pública, Universidad de Pamplona).

Su objetivo es que **otra persona investigadora pueda entender, verificar y reutilizar los datos de la revisión sin tener que consultar al autor**: qué estudios se incluyeron, de dónde provienen, cómo se seleccionaron y con qué criterios se clasificaron.

## 🌱 Origen

- **Fuentes:** búsquedas en **Scopus** y **PubMed** realizadas el **10 de mayo de 2026**.
- **Método:** revisión sistemática reportada según **PRISMA 2020**, pregunta estructurada con **SPIDER**, calidad evaluada con **CASP** y **JBI**, síntesis temática de **Thomas y Harden (2008)**.
- **Construcción del dataset:** las variables se compilaron a partir de la matriz de extracción y del manuscrito de la revisión (mayo de 2026); las referencias bibliográficas se verificaron en las publicaciones originales. Ver [Metodología](docs/methodology.md).

## 🗺️ Alcance

| Dimensión | Cobertura |
|---|---|
| Unidad de análisis | Estudio publicado (1 fila = 1 estudio incluido) |
| Número de registros | 20 estudios incluidos · 13 pasos del flujo PRISMA |
| Periodo de búsqueda | 1 ene 2006 – 10 may 2026 (estudios incluidos: 2010–2025) |
| Cobertura geográfica | 11 países + la región del Caribe + 3 estudios globales/multilaterales |
| Idiomas admitidos | Español, inglés, portugués |
| Tema | Gobernanza territorial de la APS × equidad / determinación social de la salud |

## ⚠️ Límites

- **Solo dos bases de datos** (Scopus y PubMed): pueden faltar estudios indexados en LILACS, SciELO o literatura gris.
- **Protocolo sin registro previo en PROSPERO.**
- **Ningún estudio incluido analiza Colombia**: el dataset describe evidencia internacional, no el contexto de Cúcuta.
- **No incluye los 118 registros originales** de la búsqueda ni los textos completos de los artículos, por las condiciones de uso de las bases de datos; están disponibles bajo solicitud razonable al autor (ver [nota sobre datos crudos](data/raw/README.md)).
- Algunas variables son **derivadas** (región OMS, categoría de diseño, herramienta de calidad); sus reglas de derivación están en el [Diccionario de datos](docs/data_dictionary.md).

---

## 📁 Estructura

```
📦 Repositorio_Datos_Tesis_APS_Cucuta/
├── README.md                         # Propósito, origen, alcance y límites
├── INICIO.md                         # Índice de navegación
├── LICENSE                           # Condiciones de reutilización (CC BY 4.0)
├── CHANGELOG.md                      # Historial de versiones
├── CITATION.cff                      # Metadatos de cita
├── datapackage.json                  # Esquema y metadatos (Frictionless Data)
├── data/
│   ├── raw/README.md                 # Nota sobre los registros originales
│   └── processed/
│       ├── estudios_incluidos.csv    # ★ Dataset principal (20 estudios)
│       └── flujo_prisma.csv          # Flujo de selección PRISMA 2020
├── docs/
│   ├── README.md                     # Libro de códigos (codebook) y vista previa
│   ├── data_dictionary.md            # Diccionario de datos
│   ├── methodology.md                # Metodología
│   ├── quality_report.md             # Reporte de calidad
│   ├── ethical_considerations.md     # Consideraciones éticas y derechos
│   └── figuras/                      # Diagrama PRISMA 2020 (PNG y SVG)
├── metadata/
│   ├── schemaorg.jsonld              # Metadatos Schema.org
│   └── dcat.ttl                      # Metadatos DCAT
└── fair/README.md                    # Declaración FAIR
```

## 🔍 Uso

1. Abra `data/processed/estudios_incluidos.csv` con la herramienta de su preferencia (R, Python, Excel, SPSS). En Excel: *Datos → Desde texto/CSV → Origen: UTF-8*.
2. Consulte el [diccionario de datos](docs/data_dictionary.md) antes de analizar.
3. `flujo_prisma.csv` es un resumen agregado sin llave común con la tabla de estudios; su paso `P13` (n = 20) corresponde al total de filas de `estudios_incluidos.csv`.

## 🧬 FAIR

Ver la [declaración FAIR](fair/README.md). Formatos abiertos, documentación, licencia y metadatos estructurados disponibles; el dataset aún no cuenta con DOI.

## 📖 Cita

> Quiroz Ortega, J. F. (2026). *Estudios incluidos en la revisión sistemática sobre gobernanza territorial de la APS y determinación social de inequidades en salud (2006–2026)* (Versión 1.0.0) [Conjunto de datos]. Universidad de Pamplona.

Ver `CITATION.cff` para el formato estructurado.

## 📜 Licencia

Datos y documentación bajo **Creative Commons Atribución 4.0 Internacional (CC BY 4.0)**. Ver [LICENSE](LICENSE) y las [consideraciones éticas](docs/ethical_considerations.md).

## 📬 Contacto

**Jose Fred Quiroz Ortega** — Doctorado en Salud Pública, Universidad de Pamplona  
ORCID: [0000-0002-1741-6067](https://orcid.org/0000-0002-1741-6067) · jfquiroz26@gmail.com
