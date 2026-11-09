# 🏠 Inicio: Repositorio de datos de la tesis

**Tesis:** Gobernanza territorial de la APS y determinación social de inequidades en salud — Cúcuta, Norte de Santander
**Autor:** Jose Fred Quiroz Ortega ([ORCID](https://orcid.org/0000-0002-1741-6067)) — Doctorado en Salud Pública, Universidad de Pamplona · **Versión:** 1.0 · **Actualizado:** 2026-11-08

> **Pregunta guía del curso:** ¿puede otra persona investigadora entender estos datos sin preguntarle a su creador?

---

## ✅ Entregable (plantilla RYFoR)

| Elemento | Dónde | Estado |
|---|---|---|
| `data/` — Dataset en CSV | [estudios_incluidos.csv](data/processed/estudios_incluidos.csv) · [flujo_prisma.csv](data/processed/flujo_prisma.csv) · vista previa en [Codebook](docs/README.md) | ✅ Requerido |
| `docs/` — Diccionario de datos | [Diccionario de datos](docs/data_dictionary.md) | ✅ Requerido |
| `docs/` — Metodología | [Metodología](docs/methodology.md) | ✅ Requerido |
| `README.md` — Propósito, origen, alcance, límites | [README](README.md) | ✅ Requerido |
| `LICENSE` — Condiciones de reutilización | [LICENSE](LICENSE) (CC BY 4.0) · [Verificación de derechos](docs/ethical_considerations.md) | ✅ Requerido |
| `metadata/` + `fair/` | [schemaorg.jsonld](metadata/schemaorg.jsonld) · [dcat.ttl](metadata/dcat.ttl) · [Declaración FAIR](fair/README.md) | 🔍 Explorar |
| `datapackage.json` + `CITATION.cff` | [datapackage.json](datapackage.json) · [CITATION.cff](CITATION.cff) | 🔍 Explorar |

Extras: [Reporte de calidad](docs/quality_report.md) · [CHANGELOG](CHANGELOG.md) · [Datos crudos (pendiente)](data/raw/README.md)

## 📌 Pendientes

- [ ] Publicar en Zenodo para obtener DOI

---

## 🧭 Cómo usar este repositorio en Obsidian

1. Abre Obsidian → **"Abrir carpeta como bóveda"** (*Open folder as vault*) → selecciona la carpeta `Repositorio_Datos_Tesis_APS_Cucuta`.
2. Si aparece el aviso de confianza, elige **"Confiar en el autor y activar plugins"** (no hay plugins; es solo el aviso estándar).
3. Esta nota (`INICIO.md`) es la portada. Los enlaces llevan a cada documento.
4. Los archivos `.csv`, `.json`, `.cff` y `.ttl` aparecen en el explorador de archivos porque está activado *Ajustes → Archivos y enlaces → Detectar todas las extensiones de archivo*. Al hacer clic, Obsidian los abre con el programa predeterminado del computador (Excel, editor de texto).
5. Para ver cómo se conectan los documentos: **Vista de grafo** (ícono de nodos en la barra lateral izquierda, o `Ctrl/Cmd + G`).
6. Para fijar esta nota como portada: clic derecho sobre la pestaña → **Fijar**.
