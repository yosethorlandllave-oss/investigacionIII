# Desarrollo — U3 Sesión 3: Estado del arte

**Título de la investigación:** Análisis de Sentimientos con Modelos de Lenguaje para Sistemas de Recomendación: Una Revisión Sistemática de la Literatura

**Autor:** Yoseth Orlando Llave Huachaca

**Curso:** Investigación III — Universidad Peruana Unión

**Fecha de corte:** 1 de noviembre de 2026

**Estado:** protocolo y síntesis bibliográfica documentados; borrador para integrar al Perfil de Proyecto de Investigación.

## Alcance del producto

Esta versión conserva el título original. El alcance es el análisis de sentimientos en reseñas con modelos de lenguaje para sistemas de recomendación, con énfasis de aplicación en videojuegos (Steam/Epic Games Store). El corpus combina evidencia directa de videojuegos con estudios generales sobre clasificación, recomendación y explicación; la matriz diferencia ambos niveles y no transfiere a videojuegos resultados obtenidos en otros dominios. Se distinguen clasificación de polaridad, predicción de rating/ranking, recomendación explicable y resumen de opiniones. Una mejora clasificatoria no se considera, por sí sola, una mejora recomendadora.

Se seleccionaron 13 trabajos científicos, incluidos dos antecedentes fundacionales, dos surveys y once publicaciones recientes (2022–2026; 84,6 % del corpus). Se aplicaron criterios explícitos de búsqueda, elegibilidad y extracción. El resultado constituye un avance de revisión sistemática: faltan exportaciones de bases nativas y una segunda persona para reproducir el cribado, por lo que no se declara cierre exhaustivo tipo PRISMA.

## E1. Estrategia y registro de búsqueda

### Pregunta de revisión

¿Qué métodos basados en modelos de lenguaje se han aplicado al análisis de sentimientos de reseñas para sistemas de recomendación, qué evidencia existe sobre su integración o utilidad en recomendación —con énfasis en videojuegos— y qué datos, métricas, limitaciones y brechas reporta la literatura?

Se empleó PICOC con dos estratos de búsqueda: (1) evidencia directa sobre reseñas de videojuegos/plataformas como Steam y Epic, y (2) evidencia contextual sobre modelos de lenguaje, análisis de sentimiento y recomendación en otros dominios. Se combinaron términos en inglés y español sobre sentiment analysis, aspect-based sentiment, game reviews, Steam, language models, BERT/Transformer/LLM, recommender systems, recommendation y explainable recommendation. Las búsquedas sobre Amazon, Yelp y películas se usaron para localizar antecedentes generales y se etiquetan como contextuales.

La [estrategia de búsqueda](evidencias/busqueda/estrategia_registro.md) conserva PICOC, cadenas por bloques, ventana, etapas, snowballing y candidatos pendientes. Las [consultas ejecutadas](evidencias/busqueda/consultas_ejecutadas.json) registran búsquedas por frase, DOI, dominio y fuente primaria. Se documenta lo efectivamente consultado; no se inventan exportaciones ni recuentos de bases que no se obtuvieron.

## E2. Criterios de selección y calidad

Se incluyeron trabajos con metadatos verificables y suficiente información sobre sentimiento en reseñas, integración textual en recomendación, explicación/síntesis basada en opiniones o surveys de esas tareas. La ventana fue 2022–2026. Pang et al. (2002) y Zheng et al. (2017) se admitieron por su papel fundacional en clasificación sentimental y recomendación con reseñas. Se conservaron publicaciones en inglés porque el campo y sus benchmarks son multilingües.

La evaluación considera pertinencia, método/datos, validez de etiquetas, partición y métrica, limitaciones, disponibilidad declarada y venue. No se sumaron puntos de calidad sin justificación. La categoría del venue, índice y año deben quedar identificados; cuando no se verificó una categoría de ranking, se dice así y se utiliza un juicio reservado. Véase [criterios de calidad](evidencias/busqueda/criterios_calidad.md).

El corpus de síntesis tiene **13 publicaciones únicas: 11 de 2022–2026 (84,6 %) y dos antecedentes fundacionales**. Este porcentaje describe actualidad dentro del corpus seleccionado, no exhaustividad del campo. R05 y R13 son evidencia empírica directa sobre sentimiento en reseñas de Steam; ninguno mide si el uso de esas etiquetas mejora una recomendación personalizada. Los demás trabajos aportan bases generales o evidencia contextual sobre sentimiento, recomendación, explicación y síntesis. Los candidatos todavía no verificados se mantienen fuera del corpus.

## E3. Matriz de síntesis

La [matriz de R01–R13](evidencias/matrices/matriz_sintesis.md) incluye propósito, modelo, dataset, tipo de etiqueta, tarea, métrica, resultados extraídos, limitaciones y fuente primaria. `NR` significa no reportado o no verificado en el pasaje consultado. No se descargaron o ejecutaron códigos/datasets de terceros; las disponibilidades se califican como declaraciones del artículo.

### E4. Antecedentes seminales y surveys

- **R01 — Pang, Lee y Vaithyanathan (2002):** antecedente fundacional para clasificación supervisada de polaridad en reseñas. Establece la línea histórica de clasificación, pero no integra sentimientos en recomendación.
- **R02 — Zheng, Noroozi y Yu (2017):** DeepCoNN es antecedente fundacional de usar reseñas textuales para representar usuario e ítem en predicción recomendadora. No se describe como Transformer ni como clasificador de polaridad.
- **R08 — Zhang et al. (2023):** survey de análisis sentimental por aspecto, que permite distinguir sentimiento general de opiniones asociadas a características.
- **R11 — Wu et al. (2024):** survey más directo sobre LLM y recomendación, con familias discriminativas/generativas y retos del campo.

Los dos surveys complementan funciones distintas: tareas de sentimiento por aspecto y arquitectura de recomendación. Ninguno presenta un resultado experimental único que pueda compararse con los clasificadores.

## E5. Taxonomía o mapa de literatura

La [taxonomía](evidencias/mapas/taxonomia.md) ordena la secuencia conceptual desde la reseña hasta la recomendación:

| Categoría | Trabajos | Objeto principal |
|---|---|---|
| Clasificación sentimental de reseñas | R01, R03–R05, R12–R13 | Predecir polaridad; en algunos estudios la etiqueta se deriva del rating. |
| Reseñas en recomendación y explicación | R02, R06–R07, R10–R12 | Integrar texto, estimar rating o generar explicación; R12 evalúa sentimiento en contexto recomendador, sin métricas de ranking. |
| Explicaciones y resúmenes de opinión | R06–R10 | Comunicar motivos o sintetizar evidencia textual. |
| Síntesis del campo | R08, R11 | Organizar tareas, arquitecturas y desafíos. |

Las categorías se pueden cruzar, pero sus salidas y métricas no son intercambiables. El mapa describe el corpus seleccionado, no una clasificación exhaustiva del campo entero.

## E6. Análisis crítico por categorías

### 1. Clasificación del sentimiento en reseñas

R01 introduce una comparación supervisada clásica. R03 explora ensambles de RoBERTa y recurrentes en varios datasets; R04 compara SVM y BERT en reseñas Yelp etiquetadas mediante extremos del rating; R05 compara BERT y variantes recurrentes en reseñas de Steam; R13 prueba un ensamble de métodos léxicos y SBERT ajustado sobre 147 586 reseñas de Steam y reporta F1 de 94,0 %. R12 evalúa LLM para clasificar sentimiento derivado de ratings de compra. Las diferencias de dominio, etiqueta, configuración y protocolo impiden ordenar directamente las cifras.

Las métricas F1 y accuracy de distintos conjuntos no ordenan modelos de manera válida. Si los ratings se convierten a polaridad, la etiqueta es un proxy de la valoración y puede ocultar ironía, opiniones mixtas o diferencias entre aspectos. R05 y R13 son directamente pertinentes al dominio de videojuegos, pero miden clasificación y no la utilidad de una recomendación personalizada. R13 reporta protocolos distintos en secciones diferentes (partición 80/20 y validación cruzada de cinco pliegues) y un umbral p<0,07; esto limita la interpretación de su comparación estadística. R12 añade costos de LLM para sentimiento basado en reseñas de productos, no una evaluación de ranking recomendador.

### 2. Incorporación de reseñas en recomendaciones

DeepCoNN modela reseñas de usuario e ítem y predice ratings. PEPLER adapta modelos preentrenados con prompts para recomendación explicable, y PRAG recupera reseñas para producir justificaciones y estimar rating. XRec combina señales colaborativas y capacidad lingüística para explicar perfiles. R12 estudia estrategias de clasificación sentimental sobre reseñas de compra, con ratings como etiquetas, pero no informa métricas de ranking de un recomendador.

Los artículos orientados a rating informan RMSE/MSE; los de clasificación informan accuracy/F1. Una disminución del error de rating no indica necesariamente mejor clasificación sentimental, y al revés. Para sostener que el análisis de sentimientos contribuye al sistema, el estudio debe evaluar también el resultado recomendador con comparadores pertinentes y describir la señal textual utilizada.

### 3. Explicación y síntesis de opiniones

PEPLER, PRAG y XRec generan explicaciones en contexto recomendador. HIRO selecciona grupos de reseñas y produce resúmenes fundamentados; no estima por sí solo qué ítem recomendar. Zhang et al. sitúan la extracción de aspectos y polaridad como una tarea más fina. Las explicaciones requieren medir fidelidad a reseñas, cobertura y utilidad legible; fluidez lingüística por sí sola no confirma que la explicación sea verdadera.

### 4. Síntesis de surveys

Zhang et al. organiza elementos de sentimiento por aspecto, mientras Wu et al. clasifica paradigmas de LLM para recomendación. Sus ámbitos complementarios ayudan a explicar por qué el corpus es heterogéneo. La síntesis de esta revisión, por lo tanto, conserva la tarea exacta de cada resultado y no calcula una puntuación promedio entre estudios.

## E7. Brecha de investigación sustentada

**Brecha del estado del arte:** los estudios se distribuyen entre (a) clasificar el sentimiento de reseñas, (b) incorporar texto para estimar ratings/recomendaciones y (c) explicar o resumir opiniones. La relación empírica entre esos eslabones aún requiere una síntesis comparativa y trazable que identifique cuándo la señal sentimental aporta al resultado downstream y cómo se ponderan calidad, fidelidad, dominio, costo y eficiencia.

La brecha se acota con evidencia concreta: R05 y R13 analizan sentimiento en reseñas de Steam, pero no miden recomendación downstream; R02 y R06–R07 estudian integración de reseñas o explicación en recomendadores generales; R09 resume opiniones; R10 usa señales colaborativas para explicar; R12 compara estrategias de sentimiento en reseñas de compra y reporta costos, sin evaluar ranking personalizado. El vacío no es ausencia de estudios: falta organizar las diferencias de supervisión, dominio y tarea, identificar qué resultados son comparables y precisar qué evidencia falta para demostrar utilidad en recomendación de videojuegos. La inferencia se limita al corpus y la búsqueda documentados.

**Diferenciación del proyecto:** sintetizar la relación entre sentimiento y recomendación en una revisión sistemática, con énfasis en reseñas de videojuegos, distinguiendo evidencia directa de evidencia contextual y separando polaridad, predicción recomendadora, explicación y resumen. No se propone una arquitectura ni se presupone que Transformers o LLM superen a métodos clásicos.

## E8. Borrador de introducción y estado del arte

### Introducción

Las reseñas digitales reúnen valoraciones sobre productos y servicios en forma de texto libre y, con frecuencia, ratings numéricos. Los sistemas de recomendación pueden utilizar la interacción usuario–ítem y la información expresada en reseñas para predecir preferencias, ordenar opciones o presentar explicaciones. Los modelos de lenguaje aportan representaciones contextuales y capacidad para generar explicaciones, mientras que el análisis de sentimientos transforma expresiones valorativas en etiquetas o señales que pueden integrarse en esos sistemas.

Estas actividades están relacionadas, pero responden a preguntas distintas. Un clasificador puede predecir polaridad con buen F1 y, aun así, no mejorar el orden de recomendaciones. Un sistema puede obtener menor RMSE sin identificar correctamente los aspectos que sustentan la opinión. Una explicación puede ser fluida y no estar apoyada por las reseñas. Por ello, la literatura debe compararse según la tarea, las etiquetas, el conjunto de datos y la métrica que realmente se evalúan.

Esta revisión analiza estudios sobre modelos de lenguaje y análisis de sentimientos en reseñas para recomendación, con énfasis en videojuegos. Organiza la evidencia en clasificación, integración recomendadora, explicabilidad y síntesis de opiniones; separa trabajos directos sobre videojuegos de estudios generales usados como contexto. Busca establecer qué métodos y resultados se reportan, qué evidencia mide una recomendación downstream y qué límites impiden comparar o transferir los hallazgos.

### Modelos para clasificar sentimientos en reseñas

La línea de clasificación va desde la comparación supervisada de Pang et al. hasta ensambles neuronales y Transformers. Los estudios contemporáneos abarcan Yelp, Steam y reseñas asociadas a ratings. Aunque sus puntuaciones de F1 o accuracy ilustran el desempeño en cada caso, difieren en idioma, balance, fuente de etiquetas, configuración y partición. En particular, la derivación de positivo/negativo a partir de ratings no equivale a la anotación directa de cada expresión. Los resultados sirven como evidencia de clasificación contextualizada; por sí solos no prueban impacto en recomendación.

La evidencia directa de videojuegos identificada en el corpus es Fadhlurrahman et al. (2023), que compara BERT y variantes recurrentes en reseñas de Steam. El estudio evalúa clasificación sentimental; no mide cómo las predicciones cambian el ranking o la utilidad de una recomendación. Los trabajos en otros dominios ayudan a comprender métodos y métricas, pero la transferencia a jerga, ironía y comunidades de videojuegos requiere validación específica.

### Integración del texto en recomendadores

DeepCoNN establece una vía temprana: aprender representaciones de usuarios y productos a partir de las reseñas y utilizarlas en predicción de rating. Los modelos posteriores como PEPLER y PRAG integran modelos de lenguaje y estructuras personalizadas para estimar ratings y producir explicaciones. XRec incorpora una señal colaborativa a LLM para describir perfiles y explicar interacciones. Estos estudios se evalúan por tareas recomendadoras y de generación; su resultado no puede resumirse como si fuera precisión de polaridad.

El estudio reciente de Roumeliotis et al. conecta más explícitamente sentimiento y recomendación al comparar LLM, agregadores y ensambles sobre reseñas con rating. Aporta un análisis de exactitud y costos. Sin embargo, el rating de estrellas funciona como etiqueta indirecta y los servicios cerrados vuelven sensibles al tiempo la identidad del modelo y su costo. Esta evidencia ilustra la necesidad de registrar la procedencia de etiquetas, el modelo exacto y la fecha de evaluación.

### Explicaciones y resúmenes fundamentados en reseñas

En recomendación explicable, PEPLER, PRAG y XRec buscan comunicar por qué una opción corresponde a un perfil. HIRO aborda una tarea cercana: condensar opiniones de muchas reseñas mediante selección jerárquica de evidencia y generación. El survey de Zhang et al. aporta granularidad por aspecto. En conjunto, estos trabajos muestran que personalizar una recomendación y resumir opiniones no son sinónimos. La evaluación de una explicación debe considerar que sus afirmaciones sean rastreables a reseñas, además de legibles y específicas.

### Síntesis crítica

Wu et al. organiza el uso de LLM para recomendación en paradigmas distintos y ayuda a situar estos estudios dentro de un área amplia. El survey de ABSA complementa esa taxonomía al enfocarse en elementos de opinión. La matriz de esta revisión muestra que los resultados provienen de tareas, supervisiones y objetivos heterogéneos; no corresponde comparar métricas agregadas sin armonizar datos y protocolo.

La contribución de la revisión es clarificar cómo se conectan reseña, señal sentimental y recomendación y delimitar el nivel de evidencia disponible para videojuegos. La brecha se formula como falta de síntesis comparativa entre desempeño sentimental, resultado downstream, fidelidad de explicación y costo, junto con evidencia directa aún acotada en el dominio de videojuegos. El estudio de 2026 aborda parte de esa intersección en reseñas de productos; se presenta como evidencia contextual, no como prueba sobre videojuegos.

## E9. Referencias del corpus

**R01.** Pang, B., Lee, L., & Vaithyanathan, S. (2002). Thumbs up? Sentiment Classification using Machine Learning Techniques. *Proceedings of EMNLP*, 79–86. [DOI: 10.3115/1118693.1118704](https://doi.org/10.3115/1118693.1118704).

**R02.** Zheng, L., Noroozi, V., & Yu, P. S. (2017). Joint Deep Modeling of Users and Items Using Reviews for Recommendation. *Proceedings of WSDM*, 425–434. [DOI: 10.1145/3018661.3018665](https://doi.org/10.1145/3018661.3018665).

**R03.** Tan, K. L., Lee, C. P., Lim, K. M., & Anbananthen, K. S. M. (2022). Sentiment Analysis With Ensemble Hybrid Deep Learning Model. *IEEE Access, 10*, 103694–103704. [DOI: 10.1109/ACCESS.2022.3210182](https://doi.org/10.1109/ACCESS.2022.3210182).

**R04.** Areshey, A., & Mathkour, H. (2023). Transfer Learning for Sentiment Classification Using Bidirectional Encoder Representations from Transformers (BERT) Model. *Sensors, 23*(11), 5232. [DOI: 10.3390/s23115232](https://doi.org/10.3390/s23115232).

**R05.** Fadhlurrahman, J. A. M., Herawati, N. A., Aulya, H. R. W., Puspasari, I., & Utama, N. P. (2023). Sentiment Analysis of Game Reviews on STEAM using BERT, BiLSTM, and CRF. *2023 International Conference on Electrical Engineering and Informatics (ICEEI)*, 1–6. [DOI: 10.1109/ICEEI59426.2023.10346219](https://doi.org/10.1109/ICEEI59426.2023.10346219).

**R06.** Li, L., Zhang, Y., & Chen, L. (2023). Personalized Prompt Learning for Explainable Recommendation. *ACM Transactions on Information Systems, 41*(4), Article 111. [DOI: 10.1145/3580488](https://doi.org/10.1145/3580488).

**R07.** Xie, Z., Singh, S., McAuley, J., & Majumder, B. P. (2023). Factual and Informative Review Generation for Explainable Recommendation. *Proceedings of AAAI, 37*(11), 13816–13824. [DOI: 10.1609/aaai.v37i11.26618](https://doi.org/10.1609/aaai.v37i11.26618).

**R08.** Zhang, W., Li, X., Deng, Y., Bing, L., & Lam, W. (2023). A Survey on Aspect-Based Sentiment Analysis: Tasks, Methods, and Challenges. *IEEE Transactions on Knowledge and Data Engineering, 35*(11), 11019–11038. [DOI: 10.1109/TKDE.2022.3230975](https://doi.org/10.1109/TKDE.2022.3230975).

**R09.** Hosking, T., Tang, H., & Lapata, M. (2024). Hierarchical Indexing for Retrieval-Augmented Opinion Summarization. *Transactions of the Association for Computational Linguistics, 12*, 1533–1555. [DOI: 10.1162/tacl_a_00703](https://doi.org/10.1162/tacl_a_00703).

**R10.** Ma, Q., Ren, X., & Huang, C. (2024). XRec: Large Language Models for Explainable Recommendation. *Findings of the Association for Computational Linguistics: EMNLP 2024*, 391–402. [DOI: 10.18653/v1/2024.findings-emnlp.22](https://doi.org/10.18653/v1/2024.findings-emnlp.22).

**R11.** Wu, L., Zheng, Z., Qiu, Z., Wang, H., Gu, H., Shen, T., Qin, C., Zhu, C., Zhu, H., Liu, Q., Xiong, H., & Chen, E. (2024). A Survey on Large Language Models for Recommendation. *World Wide Web, 27*, Article 60. [DOI: 10.1007/s11280-024-01291-2](https://doi.org/10.1007/s11280-024-01291-2).

**R12.** Roumeliotis, K. I., Margaris, D., Spiliotopoulos, D., & Vassilakis, C. (2026). A Large-Scale Empirical Study of LLM Orchestration and Ensemble Strategies for Sentiment Analysis in Recommender Systems. *Future Internet, 18*(2), 112. [DOI: 10.3390/fi18020112](https://doi.org/10.3390/fi18020112).

**R13.** Etemad Golestani, N., & Moattar, M. H. (2026). Lightweight hybrid adaptive weighted ensemble integrating fine-tuned SBERT with lexical and statistical models for robust Steam review sentiment classification. *Discover Computing, 29*, Article 367. [DOI: 10.1007/s10791-026-10296-6](https://doi.org/10.1007/s10791-026-10296-6).

## Control de versiones y uso en el PPI

La matriz, taxonomía y criterios respaldan E8 y E9. El título, problema, objetivos y categorías deben conservar una misma delimitación al incorporarse al PPI. El corpus puede ampliarse si un cribado formal posterior identifica publicaciones elegibles adicionales.
