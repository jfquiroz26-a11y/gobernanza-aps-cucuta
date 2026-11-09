# 📥 Datos crudos (pendiente)

Volver a [INICIO](../../INICIO.md).

Esta carpeta debe contener los **datos originales, sin modificar**, de la búsqueda del 10 de mayo de 2026. Nunca se editan: cualquier limpieza se guarda en `data/processed/`.

| Archivo sugerido | Contenido | Registros esperados |
|---|---|---|
| `scopus_export_2026-05-10.csv` | Exporte de Scopus con la ecuación de búsqueda | 102 |
| `pubmed_export_2026-05-10.csv` | Exporte de PubMed (formato CSV) | 16 |
| `cribado_decisiones.csv` | Una fila por registro con la decisión (incluido/excluido), fase y motivo | 118 |

**Cómo agregarlos:** copia los archivos desde tu libro de trabajo de cribado a esta carpeta y regístralo en [CHANGELOG](../../CHANGELOG.md).

⚠️ Antes de publicar esta carpeta, revisa [las restricciones de redistribución de Scopus](../../docs/ethical_considerations.md).
