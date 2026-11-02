# Taxonomía del corpus

El mapa agrupa las 13 publicaciones de la [matriz de síntesis](../matrices/matriz_sintesis.md) por función y nivel de pertinencia. R05 y R13 son evidencia directa de reseñas de videojuegos (Steam); los otros estudios se emplean como fundamentos o evidencia contextual general. Las categorías pueden solaparse y no expresan jerarquía de calidad.

| Etapa | Enfoque | Trabajos | Salida evaluada |
|---|---|---|---|
| 1. Interpretar texto y sentimiento | Clasificación general, clásica, neuronal y con Transformer | R01, R03–R05, R12–R13 | Polaridad; accuracy/F1/ROC-AUC. |
| 2. Representar usuario, ítem y opinión | Incorporación de reseñas o uso de sentimiento en el contexto recomendador | R02, R06–R07, R10–R12 | Rating, ranking o preferencia en R02/R06/R07/R10; R12 evalúa clasificación y costo, no ranking. |
| 3. Explicar o sintetizar | Recomendación explicable, reseñas recuperadas y opiniones por aspecto | R06–R10 | Fidelidad, cobertura, prevalencia y evaluación humana. |
| 4. Ordenar el campo | Survey de sentimiento por aspecto y survey de LLM para recomendación | R08, R11 | Taxonomías, retos y agenda de investigación. |

## Mapa conceptual

1. **Reseña**: texto libre y, en algunos datasets, rating numérico asociado.
2. **Análisis del texto**: polaridad general (R01, R03–R05, R12–R13) o aspectos específicos (R08).
3. **Representación para el usuario y el ítem**: integración de señales textuales y colaborativas (R02, R06–R07, R10); R12 estudia sentimiento asociado a recomendación, no un ranking downstream.
4. **Salida del sistema**: rating/recomendación; explicación o resumen sustentado en reseñas (R06–R10).
5. **Evaluación**: clasificador, recomendador y explicación requieren métricas diferentes.

La secuencia es una síntesis conceptual propia, no un flujo implementado por cada artículo. R09, por ejemplo, resume opiniones sin estimar recomendación personalizada; R03 clasifica sentimiento sin evaluar una recomendación downstream. Los estudios no deben presentarse como un sistema único.

## Evolución representada

| Año / tramo | Hito en este corpus |
|---|---|
| 2002 | Comparación supervisada de polaridad en reseñas (R01). |
| 2017 | Redes profundas que incorporan texto de usuario e ítem en recomendación (R02). |
| 2019 | Fundamento de preentrenamiento contextual citado para la familia BERT; antecedente metodológico, no incluido en el corpus evaluado. |
| 2022–2023 | Ensambles sentimentales, Transformers para reseñas/juegos y prompts para recomendación explicable (R03–R08). |
| 2024 | LLM para explicaciones y resúmenes fundamentados, junto con survey de LLM recomendadores (R09–R11). |
| 2026 | Comparación de estrategias de LLM para sentimiento derivado de rating dentro de recomendación, con costo explícito (R12). |
| 2026 | Ensamble híbrido SBERT y métodos léxicos en reseñas de Steam (R13); mide clasificación, no recomendación downstream. |

La cronología describe los trabajos seleccionados; no cuantifica la evolución general del campo.

## Relación con la brecha

El corpus contiene trabajos que evalúan polaridad y otros que evalúan recomendación o explicación. R05 y R13 se centran en Steam; R12 trabaja con reseñas de productos y sentimiento derivado de ratings, sin evaluar ranking downstream. La brecha de la RSL se formula como **síntesis todavía fragmentada entre calidad de análisis de sentimiento, utilidad real para recomendación, explicabilidad y eficiencia**, considerando además diferencias de dominios y supervisión. Es una interpretación de la muestra revisada, no una declaración de inexistencia absoluta.
