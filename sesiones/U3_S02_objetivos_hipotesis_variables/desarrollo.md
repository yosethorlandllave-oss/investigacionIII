# Desarrollo — U3 Sesión 2: Objetivos, hipótesis y variables

**Título de la investigación:** Análisis de Sentimientos con Modelos de Lenguaje para Sistemas de Recomendación: Una Revisión Sistemática de la Literatura

**Autor:** Yoseth Orlando Llave Huachaca

**Curso:** Investigación III — Universidad Peruana Unión

**Fecha:** 1 de noviembre de 2026

**Estado:** objetivos y matriz de consistencia para el diseño documental de la revisión; no hay experimento propio.

## E1. Pregunta de investigación revisada

**Brecha:** los estudios de clasificación, recomendación y explicación emplean tareas y métricas distintas, y la evidencia directamente enfocada en videojuegos es reducida frente a la literatura general. Se requiere sintetizar qué resultados son directos, cuáles son contextuales y qué límites afectan su transferencia.

**Pregunta:** ¿Qué métodos basados en modelos de lenguaje se han aplicado al análisis de sentimientos de reseñas para sistemas de recomendación, qué evidencia existe sobre su integración o utilidad en recomendación —con énfasis en videojuegos— y qué datos, métricas, limitaciones y brechas reporta la literatura?

La pregunta delimita población documental, enfoques, contexto y resultados. Se responde mediante búsqueda y síntesis crítica, no mediante una intervención computacional propia.

## E2. Objetivo general

Analizar sistemáticamente la literatura científica sobre modelos de lenguaje y análisis de sentimientos en reseñas para sistemas de recomendación, con énfasis en videojuegos, comparando métodos, dominios, datos, métricas, resultados, limitaciones y brechas reportadas.

## E3. Objetivos específicos

| Código | Objetivo | Resultado verificable |
|---|---|---|
| OE1 | Diseñar y documentar la búsqueda, los criterios de selección y el registro de selección de estudios pertinentes. | Cadenas, fechas, criterios, registro de acceso y corpus identificable. |
| OE2 | Clasificar los estudios según la función del análisis de sentimientos/modelo de lenguaje y su relación con recomendación, ranking, explicación o resumen. | Taxonomía temática con asignación razonada de publicaciones. |
| OE3 | Comparar datasets, etiquetas, modelos, métricas, resultados y recursos de reproducibilidad, distinguiendo cada tarea evaluada. | Matriz de extracción y síntesis de métodos y evaluación. |
| OE4 | Sintetizar limitaciones, condiciones de transferencia y brechas de investigación a partir de la evidencia seleccionada. | Estado del arte por categorías y brecha sustentada. |

## E4. Necesidad de hipótesis

La consigna solicita determinar si el enfoque y alcance requieren hipótesis. Este trabajo es una revisión bibliográfica, con síntesis descriptiva y crítica de publicaciones. No manipula variables ni contrasta experimentalmente el desempeño de modelos sobre un nuevo dataset. Por ello, **no corresponde formular hipótesis general, H0 ni hipótesis específicas**. Los hallazgos se organizan mediante preguntas guía y categorías de extracción; no se presentan relaciones causales.

## E5. Variables y categorías de análisis

Las categorías siguientes son constructos de extracción documental, no variables independientes/dependientes del experimento. La unidad de análisis es el artículo o estudio elegible. Se registra “no reportado” si la publicación no permite codificar un campo.

| Categoría analítica | Función en la revisión | Valores/códigos iniciales |
|---|---|---|
| Función del análisis sentimental | Identificar qué se hace con la opinión | Clasificación; análisis por aspecto; señal de rating/preferencia; explicación; resumen; múltiple. |
| Familia de modelo | Describir el método | Léxico; ML tradicional; CNN/RNN; Transformer; LLM generativo; híbrido/ensamble. |
| Vínculo con recomendación | Distinguir nivel de integración | Clasificador aislado; atributo de usuario/ítem; predicción de rating; ranking; explicación; resumen; evaluación downstream. |
| Datos y etiquetas | Entender evidencia y supervisión | Dominio/plataforma/idioma; tamaño; etiqueta manual, rating-proxy, débil o no supervisada; partición. |
| Evaluación | Comparar solo resultados compatibles | Accuracy, precision/recall/F1; RMSE/MSE; ranking; evaluación humana; costo/latencia. |
| Reproducibilidad y límites | Valorar trazabilidad | Código/datos/modelo declarados; split; recursos; limitaciones; sesgo o transferibilidad. |

## E6. Matriz de operacionalización documental

| Categoría | Definición conceptual | Definición operacional / indicador | Escala | Fuente/instrumento |
|---|---|---|---|---|
| Función de sentimiento | Papel que cumple la inferencia u organización de opinión | Codificar función primaria y secundaria de cada estudio usando la taxonomía; registrar evidencia textual y localizador. | Nominal multietiqueta. | Artículo primario; ficha de extracción. |
| Familia de modelo | Arquitectura o método aplicado al texto | Registrar método descrito por autores y si integra modelos; no inferir arquitectura por solo nombrar LLM. | Nominal, multietiqueta. | Sección método/modelo; matriz. |
| Vínculo recomendador | Relación técnica entre texto de opinión y resultado recomendador | Clasificar si la polaridad se evalúa sola o afecta rating, ranking, explicación, resumen o decisión final. | Nominal ordenada por grado de integración: indirecto/directo; añadir subtipo nominal. | Método y evaluación; ficha de extracción. |
| Datos y referencia | Evidencia textual y mecanismo usado para construir etiquetas | Extraer tamaño, idioma, dominio, plataforma, unidad, polaridades y fuente de ground truth; marcar NR cuando falte. | Numérica para recuentos; nominal para procedencia y tipo de etiqueta. | Dataset/sección experimental; matriz. |
| Resultado/métrica | Medida de una tarea específica | Copiar métrica, partición y valor con clase/escala; asociarla a clasificación, recomendación o explicación. No fusionar métricas. | Según métrica publicada; variable numérica continua para cada indicador. | Tablas y resultados; ficha de extracción. |
| Calidad/reportabilidad | Información para evaluar validez y reproducción | Codificar criterios A–F de la revisión cualitativamente; registrar código/datos, limitaciones y fuente verificable. | Ordinal por ítem: sí/parcial/no/no reportado; sin suma automática. | Texto completo, fuentes del venue, lista de calidad. |

**Procedimiento:** un lector completa la ficha con localizador por campo; campos dudosos pasan a revisión manual. La disponibilidad declarada no equivale a replicación. Las métricas se conservan en unidades originales y se comparan cualitativamente por tarea.

## E7. Matriz de consistencia

| Problema / pregunta | Objetivo general | OE | Hipótesis | Categoría / indicador | Fuente |
|---|---|---|---|---|---|
| Evidencia dispersa sobre modelos de lenguaje, sentimiento en reseñas y recomendación. ¿Cómo se aplican, evalúan y qué límites reportan? | Analizar sistemáticamente la literatura y comparar sus aplicaciones y evaluación. | OE1: diseñar y documentar búsqueda y selección. | No aplica; revisión documental. | Estrategia, criterios, fecha, registro de selección. | Consultas y metadatos. |
| La función del análisis sentimental varía entre clasificación y uso downstream. | Mismo objetivo general. | OE2: organizar categorías temáticas. | No aplica. | Función, modelo y vínculo con recomendación. | Texto primario, sección método. |
| Las métricas clasificatorias y recomendadoras no son equivalentes. | Mismo objetivo general. | OE3: comparar datos, evaluación y resultados. | No aplica. | Dataset, etiquetas, métrica, valor, split, localizador. | Tablas y sección experimental. |
| Quedan límites y brechas por sintetizar en contexto. | Mismo objetivo general. | OE4: formular síntesis y brechas. | No aplica. | Calidad, limitación, transferencia, reproducibilidad. | Discusión/conclusiones y criterios de calidad. |

## E8. Referencias base para definir categorías

Pang et al. (2002) aporta clasificación de polaridad; Zheng et al. (2017) integra reseñas en recomendación; Zhang et al. (2023) organiza análisis por aspecto; Wu et al. (2024) organiza modelos de lenguaje en recomendación; Roumeliotis et al. (2026) mide sentimiento, agregación y costo en ese contexto. Los metadatos y enlaces completos están en E9 de la sesión 3 y en la matriz de síntesis. Esta operacionalización es una propuesta de la revisión, no una definición atribuida literalmente a esos artículos.

## Correspondencia con la actividad

- [x] Pregunta específica, revisable y delimitada al título con énfasis en videojuegos.
- [x] Objetivo general y cuatro objetivos específicos.
- [x] Decisión explícita sobre por qué no corresponden hipótesis experimentales.
- [x] Categorías documentales, definiciones y operacionalización con indicadores, escala e instrumento.
- [x] Matriz de consistencia.
- [x] Fuentes científicas vinculadas con las categorías.
