# Guía para exponer — U3 Sesión 3: Estado del arte

**Título:** *Análisis de Sentimientos con Modelos de Lenguaje para Sistemas de Recomendación: Una Revisión Sistemática de la Literatura*  
**Duración sugerida:** 6–8 minutos.  
**Propósito:** explicar el problema, el método de búsqueda, la síntesis, la brecha y el valor de la revisión con afirmaciones verificables en el repositorio.

## Idea central

La literatura ofrece métodos para clasificar sentimientos en reseñas y métodos para usar reseñas en recomendadores. Sin embargo, miden tareas distintas. En el corpus seleccionado, el estudio de Steam es evidencia directa de clasificación de reseñas de videojuegos, pero no mide el efecto de esa clasificación sobre una recomendación. Los trabajos de otros dominios sirven como contexto, no como prueba directa para videojuegos.

## Secuencia de exposición

### Diapositiva 1 — Tema y delimitación (45 segundos)

**En pantalla:** título, problema y pregunta de revisión.

**Guion:** “Nuestro tema es el análisis de sentimientos con modelos de lenguaje para sistemas de recomendación. Conservamos el título original y damos énfasis a videojuegos porque las reseñas de Steam expresan opiniones sobre jugabilidad, historia, gráficos y rendimiento. La revisión incluye evidencia general de recomendación como contexto, pero distingue esos estudios de los que sí trabajan con videojuegos.”

**Pregunta:** ¿Qué métodos basados en modelos de lenguaje se han aplicado al análisis de sentimientos de reseñas para sistemas de recomendación, qué evidencia existe sobre su integración o utilidad en recomendación —con énfasis en videojuegos— y qué datos, métricas, limitaciones y brechas reporta la literatura?

### Diapositiva 2 — Problema y relevancia (60 segundos)

**En pantalla:** “clasificación ≠ recomendación” y tres tareas: polaridad, ranking/rating, explicación.

**Guion:** “La situación problemática es la fragmentación de la evidencia. Un modelo puede obtener buen F1 al clasificar reseñas, pero ese dato no prueba que un recomendador ordene mejor los juegos. De manera similar, un menor RMSE de rating no demuestra que el modelo interprete correctamente el sentimiento. La revisión es relevante porque separa estas tareas y permite saber qué se midió realmente.”

### Diapositiva 3 — Búsqueda y selección (60 segundos)

**En pantalla:** PICOC en dos niveles: evidencia directa de videojuegos y evidencia contextual; criterios de selección; snowballing.

**Guion:** “Definimos búsquedas para reseñas de videojuegos, Steam y recomendación, y búsquedas complementarias para sentimiento y recomendación en otros dominios. Registramos las consultas, criterios, fuentes y rastreo de referencias. Seleccionamos 13 publicaciones únicas: once de 2022 a 2026 y dos antecedentes fundacionales. Ese porcentaje indica actualidad del corpus; no significa que la búsqueda cubra exhaustivamente toda la literatura.”

### Diapositiva 4 — Qué contiene la evidencia (75 segundos)

**En pantalla:** tres categorías: clasificación, integración en recomendadores, explicación/síntesis.

**Guion:** “La matriz compara métodos, datos, etiquetas, tareas, métricas, resultados y limitaciones. Pang y DeepCoNN aportan antecedentes fundacionales de clasificación sentimental e integración de reseñas en recomendación. El survey de Zhang organiza análisis por aspectos y el survey de Wu estudia modelos de lenguaje en recomendación. Fadhlurrahman y sus coautores comparan BERT y variantes BiLSTM/CRF en reseñas de Steam. Etemad Golestani y Moattar estudian un ensamble con SBERT ajustado en 147 586 reseñas de 160 juegos y reportan F1 de 94 %. Ambos trabajos miden clasificación, no utilidad recomendadora. PEPLER, PRAG, XRec y HIRO aportan evidencia contextual sobre recomendación explicable o resumen de opiniones, principalmente fuera de los videojuegos.”

### Diapositiva 5 — Análisis crítico y brecha (75 segundos)

**En pantalla:** mapa: reseña → señal sentimental → recomendación/explicación → evaluación.

**Guion:** “La comparación muestra tres límites. Primero, las etiquetas a veces se derivan de estrellas, que son una aproximación y no anotación directa del sentimiento expresado. Segundo, las métricas no son intercambiables: accuracy/F1 evalúan clasificación, RMSE/MSE evalúan rating, y las explicaciones requieren medidas propias o evaluación humana. Tercero, la evidencia directa sobre videojuegos es reducida y el estudio de Steam no evalúa recomendación downstream. La brecha sustentada es la necesidad de una síntesis que conecte esas etapas y establezca qué resultados son comparables y cuáles todavía no se han validado en videojuegos.”

### Diapositiva 6 — Contribución, límites y cierre (60 segundos)

**En pantalla:** aporte y limitaciones metodológicas actuales.

**Guion:** “La contribución es una taxonomía y comparación trazable que evita atribuir a un dominio resultados obtenidos en otro. La entrega registra 12 artículos, búsquedas, criterios, matriz, mapa y referencias. Es un avance de revisión sistemática, no una declaración de búsqueda PRISMA cerrada: para el cierre se necesitan exportaciones nativas de bases académicas y un segundo cribador independiente. El siguiente paso es completar ese cribado y ampliar la búsqueda directa de recomendación de videojuegos.”

## Preguntas probables del docente

**¿Por qué incluyen trabajos de Amazon, Yelp o películas si el énfasis es videojuegos?**  
Porque aportan métodos generales de análisis sentimental, uso de reseñas y recomendación. La matriz los identifica como evidencia contextual; no se usan para afirmar que el mismo desempeño se obtiene en reseñas de videojuegos.

**¿Por qué no formularon hipótesis?**  
El producto es una revisión documental. No entrenamos ni comparamos modelos sobre un nuevo conjunto de datos; organizamos y analizamos resultados publicados. Por eso usamos preguntas y categorías de extracción, no hipótesis causales experimentales.

**¿El 95,2 % de F1 prueba que las recomendaciones mejoran?**  
No. Ese valor corresponde a clasificación de sentimiento en el estudio de Steam. Para demostrar una mejora recomendadora habría que integrar la señal al sistema y evaluar el ranking o la utilidad de recomendación con comparadores adecuados.

**¿Los 12 artículos representan todo el campo?**  
No se afirma exhaustividad. Son el corpus documentado para este avance. Se declaran las tareas pendientes para concluir una revisión exhaustiva: exportaciones bibliográficas, registro cuantitativo de cribado y verificación independiente.

**¿Cómo justifican la brecha si hay un artículo que trata sentimiento en recomendación?**  
La brecha no es ausencia absoluta de estudios. Hay evidencia relacionada, incluso una evaluación general reciente; la brecha es que los resultados se refieren a tareas, dominios y supervisiones distintas y no resuelven todavía la transferencia a recomendación de videojuegos.

## Lista rápida antes de exponer

- [ ] Mantener el título original exactamente como aparece en el PPI.
- [ ] Explicar desde el inicio que videojuegos es el énfasis, no el único dominio del título.
- [ ] Diferenciar evidencia directa (Steam) de literatura contextual general.
- [ ] No presentar el porcentaje de actualidad como prueba de exhaustividad.
- [ ] No equiparar F1/accuracy con calidad de recomendación ni RMSE con sentimiento.
- [ ] No afirmar que el estudio de Steam mejora recomendaciones.
- [ ] Mencionar la limitación de búsqueda y el siguiente paso sin exagerar resultados.
- [ ] Tener abierta la matriz y la estrategia de búsqueda para respaldar preguntas.

## Correspondencia con las rúbricas

| Rúbrica / evidencia | Dónde se muestra durante la exposición |
|---|---|
| U3-S01: tema, problema, evidencia, brecha, pregunta y justificación | Diapositivas 1–2 y 5; [desarrollo de sesión 1](../U3_S01_problema_justificacion/desarrollo.md). |
| U3-S02: pregunta, objetivos, decisión de hipótesis y categorías | Diapositivas 1 y 6; [desarrollo de sesión 2](../U3_S02_objetivos_hipotesis_variables/desarrollo.md). |
| U3-S03: búsqueda, criterios, matriz, seminales/surveys, taxonomía, análisis y referencias | Diapositivas 3–6; [estrategia](evidencias/busqueda/estrategia_registro.md), [matriz](evidencias/matrices/matriz_sintesis.md) y [taxonomía](evidencias/mapas/taxonomia.md). |

