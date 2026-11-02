# Desarrollo — U3 Sesión 1: Identificación del problema y justificación

**Título de la investigación:** Análisis de Sentimientos con Modelos de Lenguaje para Sistemas de Recomendación: Una Revisión Sistemática de la Literatura

**Autor:** Yoseth Orlando Llave Huachaca

**Curso:** Investigación III — Universidad Peruana Unión

**Fecha:** 1 de noviembre de 2026

**Estado:** formulación del problema de revisión, para integrar al PPI.

## E1. Tema de investigación

La revisión estudia cómo los modelos de lenguaje analizan sentimientos en reseñas y cómo esa información se relaciona con sistemas de recomendación. Conserva el alcance amplio del título y toma las reseñas de videojuegos como énfasis de aplicación; Steam es el caso directo identificado en el corpus. Los trabajos de otros dominios se usan como antecedentes metodológicos o comparativos y se etiquetan como evidencia contextual, no como evidencia directa sobre videojuegos. La revisión diferencia clasificación de polaridad, predicción de preferencias, recomendación, explicación y resumen, porque son tareas con resultados distintos.

## E2. Contexto y situación problemática

Las reseñas en línea contienen expresiones valorativas sobre productos, servicios y contenidos. Los modelos de lenguaje permiten representar aspectos semánticos y contextualizar expresiones; los recomendadores, a su vez, pueden combinar texto con ratings e interacciones para predecir preferencias o explicar resultados. Sin embargo, un buen clasificador sentimental no demuestra por sí solo que las recomendaciones mejoren: para establecerlo se debe medir el resultado downstream del sistema.

El tema se delimita en dos niveles: el fenómeno central es el análisis de sentimientos de reseñas con modelos de lenguaje; la aplicación de interés son los sistemas de recomendación, con énfasis en videojuegos y reseñas de Steam/Epic Games Store. Como la literatura de integración entre sentimiento y recomendación en videojuegos es más acotada, se incorporan trabajos generales de recomendación y de clasificación como evidencia contextual, identificando explícitamente su dominio y nivel de relación. Así se conserva el título original sin atribuir a los videojuegos resultados obtenidos en comercio, películas u otros dominios.

La literatura localizada también usa distintas unidades y métricas: F1 o accuracy para clasificar polaridad; MSE/RMSE para predicción de ratings; ranking para calidad de recomendación; y medidas automáticas o evaluación humana para explicaciones. Compararlas como si midieran el mismo fenómeno puede llevar a conclusiones erróneas. La situación problemática es que la evidencia está repartida entre clasificación de sentimientos, integración de reseñas en recomendadores y generación de explicaciones. Los estudios usan dominios, etiquetas y métricas diferentes, y hay poca evidencia directa sobre reseñas de videojuegos que mida también el efecto en la recomendación. Por ello, no basta con comparar accuracy o F1 de clasificadores: se debe distinguir la evidencia directa de videojuegos de los antecedentes generales y comprobar qué resultado downstream midió cada estudio.

## E3. Evidencia de la existencia del problema

| Evidencia primaria | Hallazgo útil para delimitar el problema | Límite |
|---|---|---|
| Pang et al. (2002), reseñas cinematográficas | Compara clasificadores supervisados de polaridad, incluido SVM. | Clasificación de sentimiento no implica integración en recomendación. |
| Zheng et al. (2017), DeepCoNN | Integra reseñas de usuarios e ítems para predecir ratings. | Usa redes convolucionales; no es un Transformer ni mide polaridad directamente. |
| Fadhlurrahman et al. (2023), reseñas de Steam | Contrasta BERT y BiLSTM-CRF en reseñas de videojuegos. | La clasificación no mide una recomendación personalizada posterior. |
| Etemad Golestani y Moattar (2026), reseñas de Steam | Evalúa un ensamble híbrido con SBERT sobre 147 586 reseñas de 160 juegos; reporta F1=94,0 %. | Evalúa clasificación y no recomendación downstream; el artículo presenta protocolos experimentales distintos que requieren cautela. |
| Li et al. (2023), PEPLER; Xie et al. (2023), PRAG | Usan modelos preentrenados, reseñas y generación de explicaciones dentro de recomendación. | Evalúan rating y explicación con métricas distintas de clasificación sentimental. |
| Ma et al. (2024), XRec | Combina señales colaborativas y LLM para explicar comportamiento usuario–ítem. | Explicabilidad no equivale a precisión de polaridad. |
| Roumeliotis et al. (2026) | Compara LLM individuales, agregación y ensambles para clasificar sentimiento de reseñas de compra en un contexto de recomendación; reporta desempeño y costos. | La referencia de polaridad se deriva de ratings; no evalúa calidad de ranking recomendador y depende de servicios cerrados. |

La matriz de la sesión 3 consigna datasets, protocolos, métricas y resultados extraídos. También muestra que las conclusiones no son directamente comparables sin atender a las etiquetas y a la tarea evaluada.

## E4. Brecha de investigación (research gap)

**Brecha preliminar:** la evidencia se distribuye entre clasificación de sentimientos en reseñas, integración del texto en predicción de preferencias y generación de explicaciones/resúmenes. Hace falta una síntesis crítica y trazable que compare cómo se conectan esas etapas, qué señales de opinión usan los modelos de lenguaje y qué evidencia demuestra mejoras en la recomendación, junto con los costos, limitaciones y riesgos de fidelidad.

La brecha no afirma que no existan trabajos; la revisión incluye estudios directamente relacionados y uno de 2026 que evalúa sentimiento y ensambles en recomendación. La pregunta pendiente es cómo organizar y comparar esa evidencia con criterios metodológicos comunes, incluidos los artículos del borrador original que puedan verificarse. La conclusión se limita al corpus y estrategia documentados en la sesión 3.

## E5. Problema y pregunta de investigación

**Problema:** la evidencia sobre análisis de sentimientos con modelos de lenguaje y su uso en recomendación está fragmentada por tarea, dominio y métrica. Esta fragmentación dificulta determinar qué métodos se han evaluado en reseñas de videojuegos y hasta qué punto los hallazgos obtenidos en otros dominios permiten orientar sistemas de recomendación de videojuegos.

**Pregunta de investigación:** ¿Qué métodos basados en modelos de lenguaje se han aplicado al análisis de sentimientos de reseñas para sistemas de recomendación, qué evidencia existe sobre su integración o utilidad en recomendación —con énfasis en videojuegos— y qué datos, métricas, limitaciones y brechas reporta la literatura?

La pregunta es apropiada para una revisión, no para un experimento causal. Su población documental y criterios de búsqueda se delimitan en la sesión 3.

## E6. Justificación

**Científica.** La revisión organiza la relación entre clasificación sentimental y recomendación, separa evidencia sobre predicción, personalización, explicación y resumen, e identifica las condiciones bajo las cuales los resultados pueden compararse. Esto permite ubicar con precisión qué aporta cada familia de modelos y evita deducir valor recomendador a partir de F1 aislado.

**Metodológica.** El trabajo documenta la estrategia de búsqueda, selección y extracción de datos, registra las diferencias de métrica y formula una síntesis temática. La matriz facilita replicación y actualización; las limitaciones de los borradores se hacen explícitas en vez de convertir referencias incompletas en evidencia verificada.

**Práctica y tecnológica.** La síntesis puede orientar a equipos que desarrollan recomendadores basados en reseñas a elegir datos, señales, métricas y procedimientos de explicación apropiados. La revisión también organiza aspectos de costo y eficiencia cuando los estudios los reportan. Sus resultados no garantizan un aumento de satisfacción o calidad comercial; esa conclusión requeriría evaluación con usuarios y sistemas desplegados.

## E7. Referencias científicas utilizadas

La lista completa y trazable de 13 trabajos se presenta en E9 de la sesión 3. Entre las fuentes centrales se encuentran Pang et al. (2002), Zheng et al. (2017), Fadhlurrahman et al. (2023), Li et al. (2023), Xie et al. (2023), Ma et al. (2024), Wu et al. (2024), Roumeliotis et al. (2026) y Etemad Golestani y Moattar (2026). Solo se incorporan a la matriz referencias con metadatos identificables y fuente de consulta registrada.

## Control de avance

- [x] Tema y contexto delimitados al título original, con videojuegos como énfasis y distinción de evidencia contextual.
- [x] Situación problemática formulada en términos de la síntesis de evidencia.
- [x] Evidencia primaria localizada y límites explicitados.
- [x] Brecha y pregunta de revisión formuladas sin declarar ausencia universal de trabajos.
- [x] Justificaciones científica, metodológica y práctica.
- [x] Referencias trazables a la sesión 3.
