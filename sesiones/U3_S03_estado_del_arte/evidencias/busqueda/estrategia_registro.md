# Estrategia y registro de búsqueda

**Título revisado:** *Análisis de Sentimientos con Modelos de Lenguaje para Sistemas de Recomendación: Una Revisión Sistemática de la Literatura*. **Fecha de búsqueda y corte:** 1 de noviembre de 2026. **Propósito:** identificar métodos de análisis de sentimientos con modelos de lenguaje en reseñas para recomendación, con énfasis en videojuegos, y distinguir la evidencia directa de los antecedentes generales.

## Preguntas guía / PICOC

| Componente | Delimitación |
|---|---|
| Población | Reseñas y opiniones de videojuegos, en especial Steam y Epic Games Store. Estudios de otros dominios se incluyen solo como contexto comparativo. |
| Intervención | Análisis de sentimiento y modelos de lenguaje, incluidos Transformers, para representar, clasificar o generar información basada en reseñas. |
| Comparación | Métodos tradicionales, enfoques híbridos, modelos preentrenados, LLM y sistemas sin análisis de sentimiento explícito. |
| Resultados | Clasificación sentimental; precisión de rating/ranking; utilidad, fidelidad y diversidad de explicaciones; costo y eficiencia cuando se reporten. |
| Contexto | Sistemas de recomendación de videojuegos; recomendación general como contexto cuando no se identifica evidencia directa en videojuegos. |

## Términos y cadenas

Se definieron dos niveles de pertinencia: evidencia directa de reseñas de videojuegos y evidencia contextual sobre sentimiento o recomendación en otros dominios. La búsqueda mantiene ambos niveles separados para evitar generalizar hallazgos de comercio, películas u otros productos a videojuegos.

| Concepto | Palabras clave |
|---|---|
| Opinión | sentiment analysis, opinion mining, sentiment classification, aspect-based sentiment, polaridad, análisis de sentimientos |
| Texto | review, user-generated content, online review, reseña, comentario |
| Modelos | language model, pretrained language model, Transformer, BERT, LLM, SVM, TF-IDF, hybrid, ensemble |
| Recomendación | recommender system, recommendation, review-based recommendation, explainable recommendation, rating prediction |
| Aplicación directa | game review, video game review, Steam, Epic Games Store |
| Dominios contextuales | product review, Amazon, Yelp, movie review, e-commerce |

```text
Q1 directa: ("sentiment analysis" OR "opinion mining" OR "aspect-based sentiment")
    AND ("video game review" OR "game review" OR Steam OR "Epic Games Store")
    AND ("language model" OR BERT OR Transformer OR LLM)
Q2 de vínculo: ("game recommendation" OR "video game recommender")
    AND (review OR sentiment OR opinion)
    AND (model OR language OR recommendation)
Q3 contextual: ("sentiment analysis" OR "opinion mining")
    AND ("recommender system" OR recommendation OR "rating prediction")
    AND (review OR "user-generated content")
Q4: ("pretrained language model" OR Transformer OR BERT OR LLM)
    AND (sentiment OR review OR opinion)
    AND (recommender OR recommendation OR explanation)
Q5: ("explainable recommendation" OR "opinion summarization")
    AND (review OR sentiment OR "language model")
Q6: (survey OR "systematic literature review")
    AND ("sentiment analysis" OR "recommender systems" OR "language models")
```

Las expresiones anteriores son una estrategia reproducible por bloques. Las consultas efectivamente enviadas y las búsquedas de verificación quedan en [consultas_ejecutadas.json](consultas_ejecutadas.json). Se buscó por título, DOI, venue y frases en páginas académicas/editoriales accesibles. Se priorizaron ACL Anthology, IEEE, ACM, AAAI, Springer, MDPI, ACM author copies, arXiv complementario y repositorios institucionales. El registro no finge consultas nativas a Scopus, Web of Science, ScienceDirect o Semantic Scholar cuando no se exportaron desde esas plataformas.

## Fechas, criterios y selección

Fecha límite inclusiva: 1/11/2026. Ventana reciente: 2022–2026. Los dos trabajos anteriores se admiten por su papel fundacional: Pang et al. para polaridad supervisada en reseñas, y Zheng et al. para integración profunda de reseñas en recomendación. El corpus contiene 13 trabajos: once recientes (84,6 %) y dos fundacionales. El porcentaje se calcula sobre publicaciones únicas; las dos versiones consultadas del survey R11 cuentan como un solo estudio.

Se incluyeron publicaciones formales o artículos científicos con texto suficiente para identificar método, datos/tarea y resultados o alcance de síntesis; estudios de análisis sentimental de reseñas, integración de reseñas en recomendación, explicaciones/resúmenes que procesan opiniones y surveys pertinentes. Se excluyeron duplicados, documentos sin metadatos verificables y estudios de recomendación que no usaran reseñas, texto u opinión en su objeto analítico. Un candidato encontrado solo mediante resumen se conserva como pendiente, no se eleva al corpus de lectura.

| Etapa | Criterio de registro | Resultado de esta sesión |
|---|---|---|
| Detección | Título, autores, año, DOI/URL y propósito | Registro de consultas y candidatos. No se calcula un número global de hits de motores heterogéneos. |
| Deduplicación | DOI; título + autores para duplicados/versiones | R01–R13 son trabajos distintos; preprints/versiones espejo no cuentan aparte. |
| Selección | Pertinencia, tipo de fuente y datos suficientes para extracción | Matriz de 13. Se excluyen candidatos sin lectura suficiente o verificación de metadatos. |
| Calidad | Diseño, etiqueta de sentimiento, partición, métricas, limitaciones, venue y recursos | Evaluación cualitativa por dominio; véase [criterios_calidad.md](criterios_calidad.md). |

La estrategia de descubrimiento se apoyó en búsquedas web por frases y dominios, acceso a textos primarios y referencias consultadas. Se usó snowballing dirigido desde DeepCoNN, PEPLER, Wu et al. y el artículo de Steam, revisando citas y trabajos relacionados disponibles en páginas editoriales e índices. No se interpreta ese rastreo como grafo completo de citación.

## Candidatos y pendientes

El artículo de Tan et al. (2022) estudia ensambles sentimentales en IMDb/Twitter, sin conexión directa con recomendación: se conserva como candidato metodológico, no como parte de R01–R13. *Forecasting User Perception of Steam Game Reviews across Multiple Genres* (2026; DOI 10.59562/jessi.v7i3.13290) apareció durante el cribado y se deja como candidato: falta evaluar de forma suficiente el venue y el texto completo para incorporarlo. R05 y R13 son estudios directos sobre clasificación de reseñas de Steam; ambos dejan sin evaluar el impacto downstream sobre recomendación.

La cifra de 29 estudios consignada en el borrador de base no se utiliza como resultado de esta búsqueda; el corpus se contabiliza únicamente desde las publicaciones identificadas en la matriz. Esta entrega es una síntesis documentada en desarrollo: no se afirma exhaustividad PRISMA ni se inventan conteos de recuperación. Para cerrar una RSL exhaustiva se requieren exportaciones nativas de bases bibliográficas, registro de cribado y revisión independiente por una segunda persona.

## Registro de consultas

Las búsquedas ejecutadas se registraron por lotes Q01–Q08, más verificación de metadatos, venues y referencias en textos primarios. Se guardan consultas literales en JSON, con la fecha de ejecución. El buscador no proporciona en todos los casos un conteo reproducible ni los mismos filtros; por eso no se presenta un diagrama PRISMA ficticio. Se documenta el corpus efectivamente leído y los candidatos pendientes para que el equipo continúe la búsqueda formal.
