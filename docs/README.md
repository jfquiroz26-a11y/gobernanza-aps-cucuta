# 📘 Libro de códigos (codebook)

Esquema general del dataset y vista previa de los archivos CSV. Volver al [índice](../INICIO.md).

## 🧱 Tablas

### Tabla `estudios_incluidos` → `data/processed/estudios_incluidos.csv`

- **Descripción:** un registro por cada estudio incluido en la síntesis (n = 20).
- **Columnas (13):** `id_estudio`, `num_ref_manuscrito`, `autores`, `anio`, `pais_region`, `pais_iso3`, `region_oms`, `diseno_reportado`, `categoria_diseno`, `herramienta_calidad`, `foco_tematico`, `en_lista_referencias`, `referencia_completa`.
- Detalle de cada variable en [data_dictionary](data_dictionary.md).

### Tabla `flujo_prisma` → `data/processed/flujo_prisma.csv`

- **Descripción:** conteos del diagrama de flujo PRISMA 2020 (13 pasos).
- **Columnas (6):** `id_paso`, `fase`, `descripcion`, `fuente`, `n`, `motivo_exclusion`.

## 🔗 Relaciones

Sin llave común. `flujo_prisma.P13.n` = número de filas de `estudios_incluidos`.

## 📚 Convenciones

- Nombres de variables en `snake_case`, sin tildes.
- Valores de texto con tildes, en UTF-8.
- Booleanos como `true` / `false`. Vacío = no disponible / no aplica.
- Versionado semántico registrado en [CHANGELOG](../CHANGELOG.md).

---

## 👀 Vista previa: estudios incluidos (columnas principales)

| id_estudio | autores | anio | pais_region | region_oms | categoria_diseno | foco_tematico |
|---|---|---|---|---|---|---|
| E01 | Musolino et al. | 2024 | Australia | WPR | cualitativo_caso | Defensa no gubernamental (advocacy) de equidad en salud frente a barreras de gobernanza |
| E02 | van den Heever | 2025 | Sudáfrica | AFR | analisis_politica | Reformas hacia cobertura universal y arreglos de gobernanza para equidad |
| E03 | Koller & Chater | 2025 | Multipaís (rural global) | GLOBAL | cualitativo_caso | Encuadre de la equidad rural e implicaciones para gobernanza territorial |
| E04 | Barros et al. | 2018 | Multilateral (OMS) | GLOBAL | metodologico | Sistema global de monitoreo de la Declaración de Río sobre DSS |
| E05 | Tawfik-Shukor & Khoshnaw | 2010 | Iraq (Kurdistán) | EMR | cualitativo_caso | Procesos de gobernanza y política en servicios de salud en territorio post-conflicto |
| E06 | Adekoya et al. | 2023 | Canadá | AMR | cualitativo_caso | Tamizaje en APS de pobreza y DSS para fortalecer vínculos territoriales |
| E07 | Brixi et al. | 2013 | China | WPR | analisis_politica | Compromiso de gobiernos subnacionales con la equidad en salud |
| E08 | Basapathy & Mathur | 2025 | India (Karnataka) | SEAR | cualitativo_caso | Gobernanza para universalización de salud bucal en APS |
| E09 | Golechha et al. | 2025 | India | SEAR | revision | Impacto de la Misión Nacional de Salud sobre gobernanza, RHUS y sistema |
| E10 | Diehl & Langdon | 2018 | Brasil | AMR | cualitativo_caso | Participación indígena en APS: autonomía o burocratización |
| E11 | Hassell et al. | 2020 | Caribe | AMR | cualitativo_caso | Sociedad civil y rendición de cuentas para equidad (Healthy Caribbean Coalition) |
| E12 | Bergen et al. | 2019 | Etiopía | AFR | cualitativo_caso | Gestión subnacional y avance de la equidad en salud |
| E13 | Endalamaw et al. | 2025 | Etiopía | AFR | analisis_politica | Equidad en políticas de VIH/SIDA: del discurso a la operación |
| E14 | Bernal-Sundiang et al. | 2023 | Filipinas | WPR | cualitativo_caso | Gobernanza en sistemas de APS urbano, rural y remoto |
| E15 | Abimbola et al. | 2017 | Nigeria | AFR | cualitativo_caso | Gobernanza de la posta y rotación de trabajadores de APS donde no hay política formal |
| E16 | Mussa & Dagada | 2025 | Etiopía | AFR | revision | Inequidades en transformación digital de APS |
| E17 | Santric Milicevic et al. | 2024 | Multilateral (revisión) | GLOBAL | revision | Equidad de la fuerza laboral sanitaria en APS |
| E18 | Haenssgen et al. | 2024 | Laos | WPR | cualitativo_caso | Engagement comunitario y gobernanza local para equidad por confianza |
| E19 | Hove et al. | 2022 | Sudáfrica | AFR | revision | Participación comunitaria en APS y gobernanza del recurso hídrico |
| E20 | Wang et al. | 2015 | China | WPR | revision | Centros comunitarios urbanos para fortalecer APS |

## 👀 Vista previa: flujo PRISMA

| id_paso | fase | descripcion | fuente | n | motivo_exclusion |
|---|---|---|---|---|---|
| P01 | identificacion | Registros identificados | Scopus | 102 |  |
| P02 | identificacion | Registros identificados | PubMed | 16 |  |
| P03 | identificacion | Duplicados eliminados | Scopus+PubMed | 0 |  |
| P04 | identificacion | Registros excluidos antes del cribado | Scopus+PubMed | 2 | Tipo de publicación inelegible (editorial/erratum) |
| P05 | cribado | Registros cribados por título y resumen | Scopus+PubMed | 116 |  |
| P06 | cribado | Registros excluidos en cribado | Scopus+PubMed | 92 | Desalineación con los tres dominios SPIDER |
| P07 | cribado | Reportes buscados en texto completo | Scopus+PubMed | 24 |  |
| P08 | cribado | Reportes no recuperados | Scopus+PubMed | 0 |  |
| P09 | elegibilidad | Reportes evaluados para elegibilidad | Scopus+PubMed | 24 |  |
| P10 | elegibilidad | Reportes excluidos | Scopus+PubMed | 1 | Publicación duplicada en español del mismo estudio |
| P11 | elegibilidad | Reportes excluidos | Scopus+PubMed | 2 | Fuera de alcance de diseño |
| P12 | elegibilidad | Reportes excluidos | Scopus+PubMed | 1 | Fuera de alcance del fenómeno |
| P13 | inclusion | Estudios incluidos en la síntesis | Scopus+PubMed | 20 |  |

> Vista previa de solo lectura. La versión de referencia de los datos son los archivos CSV.
