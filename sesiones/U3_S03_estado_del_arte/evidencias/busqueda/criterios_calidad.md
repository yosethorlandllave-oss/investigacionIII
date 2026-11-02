# Criterios de selección y evaluación de calidad

**Fecha:** 1/11/2026. La clasificación de venue complementa la valoración del trabajo; no sustituye la revisión de método ni se proyecta retrospectivamente como garantía de calidad.

## Lista cualitativa aplicada

| Criterio | Pregunta de evaluación |
|---|---|
| A. Pertinencia | ¿El estudio analiza sentimiento en reseñas, utiliza texto/opinión para recomendación o evalúa explicaciones/resúmenes basados en reseñas? |
| B. Identificación | ¿Autores, año, título, venue y DOI/repositorio se pueden verificar? |
| C. Método y datos | ¿Se describen familia del modelo, fuente de texto y tarea? |
| D. Evaluación | ¿Se informa partición o referencia de etiquetas y métricas adecuadas a la tarea? ¿Se distingue clasificación de recomendación y de explicación? |
| E. Transparencia | ¿Se reportan limitaciones, parámetros, código o datos cuando corresponde? ¿Se diferencian recursos declarados de recursos ejecutados? |
| F. Calidad de fuente | ¿Es artículo de revista o paper revisado por pares y qué rango reciente verificable tiene el venue? |

No se aplicó una suma numérica arbitraria. Artículos con resumen indexado pero apertura directa limitada se describen conforme a la información visible; no se adjudican parámetros que no se hayan verificado. R05 se retiene por su alta pertinencia al tema de videojuegos y por estar en IEEE; su ranking CORE/Scimago específico de la conferencia ICEEI no se confirmó. La evaluación editorial de otros artículos en fuentes de acceso parcial queda limitada a metadatos y texto indexado.

## Venue e indicadores

| R# | Venue | Verificación disponible al corte | Alcance de la verificación |
|---|---|---|---|
| R01 | EMNLP | ICORE 2026 A* | Ranking actual de conferencia, no rango histórico de 2002. [CORE](https://portal.core.edu.au/conf-ranks/?by=acronym&search=EMNLP). |
| R02 | WSDM | ICORE 2026 A | Rango contemporáneo para ubicar el venue. [CORE](https://portal.core.edu.au/conf-ranks/?by=acronym&search=WSDM). |
| R03 | IEEE Access | Artículo de revista revisado por pares; indicador exacto de categoría no asentado en esta ficha | No asignar cuartil sin categoría y año reproducibles. |
| R04 | Sensors | Revista de investigación; Q por categoría/año no se usa en la selección | Mantener evaluación del artículo independiente de métricas de la revista. |
| R05 | ICEEI 2023, IEEE | Paper de conferencia publicado en proceedings IEEE; categoría CORE/CORE rank de ICEEI no verificada | Pertinencia directa, juicio de venue reservado. |
| R06 | ACM Transactions on Information Systems | AIS 2024 Q1 en Computer Science / Information Systems | Fuente pública: [clasificación UEFISCDI, edición junio 2025](https://uefiscdi.gov.ro/resource-860007-clasament.ais.jcr.2024.pdf). |
| R07 | AAAI 2023 | ICORE 2026 A* | Rango de conferencia actual, no retroactivo. [CORE](https://portal.core.edu.au/conf-ranks/?by=acronym&search=AAAI). |
| R08 | IEEE Transactions on Knowledge and Data Engineering | AIS 2024 Q1 en AI y en Information Systems | [UEFISCDI, edición junio 2025](https://uefiscdi.gov.ro/resource-860007-clasament.ais.jcr.2024.pdf). |
| R09 | Transactions of the ACL | AIS 2024 Q1 en Computer Science: Artificial Intelligence | [UEFISCDI](https://uefiscdi.gov.ro/resource-860007-clasament.ais.jcr.2024.pdf). |
| R10 | Findings of EMNLP | Artículo de proceedings ACL revisado por pares; no se transfiere un rango del evento principal sin fuente específica | Clasificación temática y experimentos pueden consultarse en el artículo. |
| R11 | World Wide Web | AIS 2024 Q2 en Computer Science / Information Systems | [UEFISCDI](https://uefiscdi.gov.ro/resource-860007-clasament.ais.jcr.2024.pdf). |
| R12 | Future Internet | Artículo de revista revisado por pares, publicado 20/02/2026; indicador de venue no asentado aquí | La novedad y datos actuales hacen especialmente necesaria una lectura crítica; el cuartil no se infiere. |
| R13 | Discover Computing, Springer Nature | Artículo de investigación de acceso abierto, publicado 22/06/2026; categoría CORE/SJR del venue no asentada aquí | Pertinencia directa a reseñas de Steam. Se conserva con cautela por inconsistencias entre los protocolos descritos (80/20 y cinco pliegues), umbral estadístico p<0,07 y ausencia de evaluación downstream. |

AIS, SJR, CiteScore y CORE son sistemas diferentes. Si el equipo quiere completar la tabla de rangos para cada venue debe registrar edición, categoría y fuente; no atribuir un mismo cuartil a todas las áreas de una revista.

## Dos antecedentes seminales y surveys

- **R01 — Pang, Lee y Vaithyanathan (2002):** estudio temprano que comparó métodos supervisados en clasificación de sentimientos; se retiene como antecedente fundacional de análisis sentimental en reseñas. No representa un modelo de lenguaje moderno ni un recomendador.
- **R02 — Zheng, Noroozi y Yu (2017):** DeepCoNN integra conjuntamente reseñas de usuario e ítem para predicción de ratings. Se retiene como antecedente fundacional del uso del texto de reseñas dentro del recomendador.
- **R08 — Zhang et al. (2023):** survey sobre tareas y métodos de análisis sentimental por aspecto; organiza granularidad, polaridad y desafíos de transferencia.
- **R11 — Wu et al. (2024):** survey más directamente relacionado con modelos de lenguaje y recomendación; separa paradigmas discriminativos y generativos y sistematiza técnicas y retos.

Se llaman seminales por su función fundacional en sus respectivas líneas, no porque sean publicaciones recientes. Los dos surveys cumplen funciones distintas y no son comparadores experimentales.
