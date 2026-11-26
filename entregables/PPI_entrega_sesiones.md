# Desarrollo — U3 Sesión 1: Problema y justificación

**Título:** Comparación de TF-IDF con SVM y BETO para clasificar sentimientos en comentarios ciudadanos sobre limpieza pública y recojo de residuos sólidos en Juliaca

**Autor:** Yoseth Orlando Llave Huachaca.

**Curso:** Investigación III, Ingeniería de Sistemas, Universidad Peruana Unión.

**Actualización:** 26 de noviembre de 2026.

**Estado:** propuesta metodológica redactada; no representa experimentos, recolección o validaciones ejecutados. El alcance de esta entrega es documental y prospectivo; la ejecución se realizará en una etapa futura.

## E1. Tema delimitado

El proyecto estudiará la clasificación automática de sentimientos en comentarios escritos en español sobre limpieza pública y recojo de residuos sólidos en Juliaca. Comparará un método tradicional, TF-IDF con máquinas de soporte vectorial (SVM), con BETO, un modelo de lenguaje preentrenado en español. TF-IDF asigna pesos a términos según su frecuencia y distribución; SVM aprende una frontera entre clases. BETO representa palabras considerando el contexto.

La unidad de análisis será el comentario, no el ciudadano. Se estudiarán tres clases: positivo, negativo y neutral. Las opiniones mixtas o indeterminables se registrarán como no clasificables para el experimento principal, sin confundirlas con neutralidad. La investigación no desarrollará recomendaciones de rutas ni medirá una mejora efectiva del servicio municipal.

## E2. Contexto y situación problemática

La municipalidad aprobó en 2024 un plan de valorización y erradicación de puntos críticos de residuos (C01). Esto sustenta la pertinencia del ámbito ambiental, pero no cuantifica opiniones o satisfacción. El documento de trabajo proporcionado propone comentarios de Facebook de la municipalidad y de Pachamama Radio, La Decana Radio y Onda Azul Puno. El acceso efectivo, los enlaces exactos de las páginas y el volumen deberán registrarse en el piloto.

El problema técnico es seleccionar un clasificador adecuado para comentarios locales, posiblemente breves, informales o con valoraciones contradictorias. Los resultados de reseñas comerciales y otros idiomas no establecen el desempeño sobre este corpus. No se conoce todavía si el costo de adaptar BETO se corresponde con una ventaja predictiva frente a SVM.

Se propone estudiar publicaciones relacionadas explícitamente con Juliaca entre noviembre de 2024 y octubre de 2026. Esta ventana procede del documento base y se confirmará antes de la recolección definitiva. La muestra digital no representa a toda la población de Juliaca.

## E3. Evidencia científica

| Fuente | Evidencia útil | Límite |
|---|---|---|
| P04 | Comparación de métodos tradicionales en comentarios peruanos de Facebook. | Restaurantes y polaridad binaria; no es prueba local. |
| P05 | Evaluación de modelos sobre español coloquial de reseñas. | Dominio cinematográfico y clasificación binaria; véase tabla verificada en S03. |
| P03 | Disponibilidad de un modelo preentrenado para español. | El preentrenamiento no garantiza éxito en sentimiento municipal. |
| P06–P07 | Evaluación de modelos clásicos/contextuales y variantes. | Condiciones experimentales y dominios distintos. |
| P08–P09 | Análisis del lenguaje de redes y de conversaciones ambientales. | Otra plataforma o problemática ambiental. |

## E4. Brecha de investigación

Los antecedentes consultados cubren clasificación en español, modelos contextuales y conversación ambiental, pero no aportan una evaluación directamente transferible a comentarios locales sobre ambos servicios de Juliaca bajo particiones comunes. La brecha del proyecto es obtener esa evidencia comparativa contextualizada. No se afirma que no exista ningún estudio equivalente en el mundo o el Perú; la búsqueda deberá ampliarse y actualizarse.

## E5. Pregunta de investigación

¿Qué diferencias de macro-F1, precisión y recall presentan TF-IDF con SVM y BETO al clasificar sentimientos en comentarios ciudadanos sobre limpieza pública y recojo de residuos sólidos en Juliaca, utilizando los mismos datos etiquetados y particiones de evaluación?

## E6. Justificación

**Científica.** Permitirá examinar si las diferencias entre representaciones estadísticas y contextuales se sostienen en un dominio local. También documentará casos donde un método sencillo resulte competitivo.

**Metodológica.** El etiquetado doble, la separación de publicaciones entre particiones y el análisis de incertidumbre harán explícitas las condiciones de comparación. Los resultados deberán interpretarse junto con su soporte y variabilidad.

**Tecnológica.** Se obtendrán pipelines reproducibles y una evaluación para elegir un componente de análisis textual. No se presupone que una arquitectura compleja sea preferible.

**Práctica.** La clasificación podría facilitar la organización de comentarios para su revisión humana. Su utilidad en decisiones municipales requeriría una evaluación posterior, distinta del desempeño lingüístico.

## E7. Referencias y evidencias

Referencias P03–P09 y C01: [bibliografía](../../literatura/referencias_ppi.md). La matriz de evidencia del problema se conserva en [evidencias](evidencias/delimitacion.md).

**Pendiente de campo:** confirmar acceso y disponibilidad del corpus. El problema no incluye cifras de reclamos ni deterioro del servicio no comprobadas.

### Delimitación del problema práctico y científico

En el plano práctico, revisar comentarios uno por uno demanda tiempo y puede producir interpretaciones diferentes. Esta es la necesidad que motiva el proyecto; todavía no se dispone de una medición municipal del tiempo de revisión y no se le asigna un valor ficticio. En el plano científico, la incertidumbre consiste en establecer qué diferencias presentan los dos clasificadores bajo un mismo conjunto de etiquetas y condiciones de evaluación.

La brecha se organiza en tres puntos: se conocen aplicaciones de clasificación en español y redes (P04, P05, P08 y P12); sus dominios y esquemas de evaluación limitan transferir los resultados; se necesita una comparación local controlada. El producto esperado es un corpus documentado de acceso restringido, dos modelos evaluados y un informe comparativo. Una aplicación municipal posterior dependerá de la calidad obtenida y de los permisos correspondientes.

### Evidencias y revisión de entrega

[Índice de evidencias](evidencias/README.md) · [Rúbrica de la sesión](../../rubricas/U3_S01_rubrica.md).

La redacción se revisó para mantener correspondencia entre problema, objetivos, indicadores y procedimiento. La aprobación académica corresponde al docente; las actividades aún no ejecutadas permanecen identificadas.


# Desarrollo — U3 Sesión 2: Objetivos, hipótesis y variables

**Título:** Comparación de TF-IDF con SVM y BETO para clasificar sentimientos en comentarios ciudadanos sobre limpieza pública y recojo de residuos sólidos en Juliaca

**Autor:** Yoseth Orlando Llave Huachaca.

**Curso:** Investigación III, Ingeniería de Sistemas, Universidad Peruana Unión.

**Actualización:** 26 de noviembre de 2026.

**Estado:** propuesta metodológica redactada; no representa experimentos, recolección o validaciones ejecutados. El alcance de esta entrega es documental y prospectivo; la ejecución se realizará en una etapa futura.

## E1. Pregunta revisada

¿Qué diferencias de macro-F1, precisión y recall presentan TF-IDF con SVM y BETO al clasificar sentimientos en comentarios ciudadanos sobre limpieza pública y recojo de residuos sólidos en Juliaca, utilizando los mismos datos etiquetados y particiones de evaluación?

## E2. Objetivo general

Comparar el desempeño de TF-IDF con SVM y BETO en la clasificación de sentimientos de comentarios ciudadanos sobre limpieza pública y recojo de residuos sólidos en Juliaca, mediante una evaluación reproducible con métricas y particiones comunes.

## E3. Objetivos específicos

| Código | Objetivo específico | Evidencia esperada |
|---|---|---|
| OE1 | Construir un corpus temático anonimizado y etiquetado mediante un protocolo de selección y anotación. | Registro de selección, guía, acuerdo y versión del corpus. |
| OE2 | Configurar y entrenar TF-IDF con SVM y ajustar BETO utilizando particiones compartidas sin fuga de información. | Configuración, manifiesto de particiones y modelos. |
| OE3 | Comparar macro-F1 y métricas por clase con estimaciones de incertidumbre bajo un protocolo predefinido. | Predicciones, métricas, diferencia y contraste. |
| OE4 | Analizar errores y limitaciones de transferencia y documentar la reproducibilidad del experimento. | Tipología de errores, ficha técnica e informe. |

## E4. Hipótesis

El antecedente P05 motiva una expectativa favorable a BETO, pero su dominio y etiquetas difieren. P12 muestra que BETO no supera siempre a alternativas especializadas. La hipótesis de investigación propone que BETO obtendrá mayor macro-F1 que SVM; es una expectativa que debe contrastarse, no un resultado.

Sea Δ = macro-F1(BETO) − macro-F1(SVM) en el mismo conjunto de prueba. Para el contraste principal se plantea H0: Δ = 0 frente a H1: Δ ≠ 0. Se usa contraste bilateral para detectar también una ventaja de SVM. Solo una diferencia positiva con evidencia estadística apoyará la expectativa de superioridad de BETO. Un resultado no significativo no prueba igualdad. No se formulan hipótesis separadas para cada objetivo instrumental.

## E5. Variables

La variable independiente será el enfoque de clasificación. La dependiente principal será macro-F1; precisión y recall por clase serán complementarios. Se controlarán corpus, etiquetas y particiones. La calidad de anotación y distribución de clases se documentarán para interpretar los resultados. El proyecto no considera satisfacción ciudadana ni eficiencia del servicio municipal como variables dependientes.

## E6. Operacionalización

| Variable | Definición conceptual y operacional | Dimensión / indicador | Escala | Instrumento |
|---|---|---|---|---|
| Independiente: enfoque de clasificación | Procedimiento que transforma texto en una clase. Dos niveles: pipeline TF-IDF–LinearSVC y BETO ajustado. | Identificador y configuración del modelo. | Nominal | Ficha experimental. |
| Dependiente principal: desempeño | Concordancia entre predicciones y etiquetas humanas revisadas. | Macro-F1: promedio no ponderado del F1 de positivo, negativo y neutral. | Numérica 0–1 | Predicciones y script de métricas. |
| Dependientes secundarias | Desempeño diferenciado por categoría. | Precision, recall y F1 por clase; exactitud y matriz de confusión. | 0–1 y recuentos | Informe de evaluación. |
| Control: datos | Mismos comentarios y etiquetas para ambos enfoques. | Hash de corpus, IDs y partición; tres clases fijas. | Nominal / recuentos | Manifiesto del corpus. |
| Control: selección de configuración | Ajuste sin acceso a prueba. | Rejilla, criterio de validación y presupuesto documentados. | Registro | Ficha experimental. |
| Calidad de anotación | Consistencia intraevaluador entre dos revisiones separadas. | Porcentaje de coincidencia entre dos revisiones del investigador y soporte por clase. | Proporciones de 0 a 1 | Ficha de revisión individual. |
| Descriptiva: recursos | Condiciones de ejecución, no parte del título ni de la hipótesis principal. | Hardware, versiones, duración y semillas. | Texto / segundos | Bitácora. |

Un corpus es un conjunto organizado de textos. Un pipeline encadena preparación y clasificación; la fuga de información ocurre cuando el ajuste utiliza datos reservados para evaluar. En cada clase, TP son aciertos positivos, FP falsas asignaciones y FN casos de la clase que el modelo omitió. Precisión mide cuántas asignaciones fueron correctas; recall, qué proporción de casos de la clase fue recuperada. F1 combina ambas medidas.

Para cada clase, precisión = TP/(TP+FP), recall = TP/(TP+FN) y F1 = 2TP/(2TP+FP+FN). Macro-F1 es el promedio de los tres F1. Se declarará zero_division=0 para cálculos indefinidos y se reportará soporte; una clase ausente en prueba obliga a revisar el diseño, no a celebrar un promedio incompleto.

## E7. Matriz de consistencia

| Problema | Objetivo | Hipótesis | Variable / indicador | Procedimiento y evidencia |
|---|---|---|---|---|
| Desempeño local no establecido en los antecedentes consultados. | Objetivo general: comparar SVM y BETO. | H0: Δ=0; H1: Δ≠0. Expectativa: Δ>0. | Enfoque; macro-F1. | Prueba común reservada y comparación pareada. |
| No existe aún un corpus local documentado en este repositorio. | OE1: construir corpus. | No requiere hipótesis independiente. | Acuerdo, soporte, elegibilidad. | Selección, anotación individual y revisión diferida. |
| Comparaciones pueden confundir datos y arquitectura. | OE2: entrenar bajo protocolo común. | Se integra al contraste general. | Configuración y partición. | Ajuste solo en entrenamiento/validación. |
| Diferencias puntuales pueden ser inestables. | OE3: evaluar e inferir. | Contraste principal general. | Δ y variabilidad. | Remuestreo agrupado y contraste descrito en S04. |
| Promedios ocultan fallos del lenguaje local. | OE4: analizar errores. | Descriptivo, sin nuevas hipótesis confirmatorias. | Errores por clase y fenómeno. | Revisión ciega de casos anonimizados. |

## E8. Referencias y trazabilidad

P01–P03 fundamentan los enfoques; P04–P08 contextualizan la comparación y M01 orienta la inferencia. Véase [bibliografía](../../literatura/referencias_ppi.md). Copias para el PPI: [operacionalización](../../ppi/02_matriz_operacionalizacion.md) y [consistencia](../../ppi/03_matriz_consistencia.md).

### Criterios para verificar los objetivos

| Objetivo | Criterio de cierre | Evidencia que debe existir |
|---|---|---|
| OE1 | Cada caso incluido tiene origen, pertinencia, etiqueta inicial y etiqueta revisada y decisión final; no quedan identificadores personales en la entrada. | Corpus restringido, guía versionada y reporte agregado de acuerdo. |
| OE2 | Ambos modelos usan el mismo manifiesto; el vocabulario y ajuste no utilizan prueba. | Configuración, versiones y registro de entrenamiento/validación. |
| OE3 | Se generan predicciones para exactamente los mismos IDs de prueba y se informa soporte por clase. | Métricas, diferencia de macro-F1 y análisis de incertidumbre. |
| OE4 | Los errores se examinan por clase y fenómeno sin volver a ajustar sobre prueba. | Ficha de errores y límites de generalización. |

El comentario constituye la unidad de observación. Las publicaciones relacionadas forman grupos para dividir los datos y estimar incertidumbre. Repetir semillas no crea ciudadanos ni publicaciones nuevas. La variable dependiente conceptual es el desempeño de clasificación; macro-F1 es su indicador principal. Las métricas secundarias describen sus dimensiones, sin multiplicar hipótesis innecesarias.

### Evidencias y revisión de entrega

[Índice de evidencias](evidencias/README.md) · [Rúbrica de la sesión](../../rubricas/U3_S02_rubrica.md).

La redacción se revisó para mantener correspondencia entre problema, objetivos, indicadores y procedimiento. La aprobación académica corresponde al docente; las actividades aún no ejecutadas permanecen identificadas.


# Desarrollo — U3 Sesión 3: Estado del arte

**Título:** Comparación de TF-IDF con SVM y BETO para clasificar sentimientos en comentarios ciudadanos sobre limpieza pública y recojo de residuos sólidos en Juliaca

**Autor:** Yoseth Orlando Llave Huachaca.

**Curso:** Investigación III, Ingeniería de Sistemas, Universidad Peruana Unión.

**Actualización:** 26 de noviembre de 2026.

**Estado:** propuesta metodológica redactada; no representa experimentos, recolección o validaciones ejecutados. El alcance de esta entrega es documental y prospectivo; la ejecución se realizará en una etapa futura.

## E1. Estrategia de búsqueda

Se realizó una búsqueda dirigida a partir de los documentos base, con consulta de fuentes originales y ampliación a fundamentos y evaluación. El [registro](evidencias/busqueda/registro_ppi.md) distingue búsquedas ejecutadas de consultas propuestas. Es un estado del arte del PPI; su cobertura es dirigida y no exhaustiva.

## E2. Selección y calidad

Se prioriza pertinencia temática o metodológica y trazabilidad. Las fuentes contextuales no sustituyen evidencia del dominio local. La [ficha de calidad](evidencias/busqueda/calidad_ppi.md) explicita el nivel de comprobación y las verificaciones editoriales pendientes. No se reproducen citas o métricas dudosas del material base.

## E3. Matriz de síntesis

Se dispone de [quince publicaciones y una fuente metodológica](evidencias/matrices/matriz_sintesis_ppi.md), organizadas por tarea, datos, aporte y límite. Son comparables por dimensiones metodológicas, no por un mismo benchmark. Falta completar localizadores y resultados numéricos en los registros marcados; la cantidad por sí sola no acredita cumplimiento pleno de E3.

## E4. Dos seminales y un survey

P01 fundamenta la comparación de clasificadores supervisados de sentimiento. P02 fundamenta la adaptación de BERT, base arquitectónica de BETO. P11 organiza tareas por aspecto y permite justificar la delimitación a polaridad global. Se conservarán como fundamentos, sin presentarlos como estudios recientes del caso local.

## E5. Taxonomía

La [taxonomía](evidencias/mapas/taxonomia_ppi.md) agrupa clasificación tradicional, modelos contextuales, ambiente, granularidad e inferencia. Sus categorías explican qué aporta cada publicación al diseño.

## E6. Tendencias, contradicciones y límites

P05 ofrece un antecedente directo SVM–BETO, pero con etiquetas binarias de cine. P12 incorpora una alternativa especializada en redes. La sofisticación del modelo no elimina el efecto del corpus ni el etiquetado. La adaptación contextual y los enfoques tradicionales deben evaluarse con la misma referencia. La evidencia ambiental disponible no demuestra por sí sola que un clasificador aprendido en reseñas prediga opiniones municipales. Macro-F1 evita que el tamaño de una clase determine por sí solo el promedio, pero requiere reportar soporte y resultados individuales.

## E7. Brecha sustentada

P04 y P05 aportan español y opinión digital, P03 y P06–P08 aportan modelado, y P09 aporta contexto ambiental. Ninguna de esas contribuciones establece el resultado de la comparación propuesta en Juliaca. La brecha se formula como evidencia local por producir, no como inexistencia universal de investigaciones. Se actualizará al ampliar búsquedas.

## E8. Estado del arte redactado

### Introducción del PPI

Los comentarios digitales pueden aportar evidencia textual sobre cómo se valora un servicio, pero su interpretación exige distinguir opiniones, información y ambigüedad. En Juliaca, el proyecto delimita esa tarea a limpieza pública y recojo de residuos. La pertinencia institucional se apoya en C01; el desempeño del clasificador requiere evidencia propia. El trabajo compara un método estadístico tradicional y un modelo contextual en español sobre una referencia humana común. La contribución prevista será una evaluación reproducible y contextualizada, sin extrapolar las opiniones digitales a toda la población.

### Métodos tradicionales y contexto peruano

La clasificación supervisada de opiniones proporciona una base para transformar textos en etiquetas (P01). En comentarios peruanos de Facebook, P04 compara métodos tradicionales y sustenta la pertinencia de SVM como referencia. El cambio desde restaurantes hacia servicios municipales exige una nueva evaluación; no se trasladan sus porcentajes al proyecto.

### Representaciones contextuales y español

BERT aporta el fundamento de adaptación de representaciones contextuales (P02) y BETO ofrece una implementación preentrenada para español (P03). P05 aborda español coloquial; P06–P07 examinan configuraciones contextuales y comparaciones de clasificación. La evidencia favorece justificar una comparación empírica, sin anticipar una ventaja fija de BETO. Los textos de redes constituyen un dominio específico de adaptación, como muestra P08.

### Aplicación ambiental y delimitación de tareas

P09 estudia conversaciones ambientales en redes. Su tarea y dominio difieren del recojo municipal, pero muestra una vía de análisis textual. P10–P11 ayudan a distinguir tareas: clasificar polaridad global no equivale a extraer cada aspecto ni a generar recomendaciones. Por ello, este perfil limita su evaluación a positivo, negativo y neutral sobre el servicio.

### Adaptación al dominio, tamaño del corpus y anotación

P12 muestra que adaptar el preentrenamiento al lenguaje social puede superar a un modelo general en español. Esta evidencia obliga a justificar BETO como candidato concreto y a reconocer modelos alternativos, sin cambiar el título aprobado. P14 refuerza que la disponibilidad de etiquetas modifica la comparación. Por ello, 600 comentarios son una meta logística preliminar y no una garantía de rendimiento.

P13 advierte que el desacuerdo entre anotadores contiene información. En este proyecto se conservarán la etiqueta inicial y su revisión y las razones de revisión de etiquetas; los casos mixtos no se convertirán artificialmente en neutrales. P09 y P15 muestran tendencias ambientales de distinto signo en dominios diferentes: no es una contradicción experimental, sino un motivo para medir el caso local.

### Síntesis crítica y propuesta

Los trabajos difieren en idioma, plataforma, etiquetas y métrica. No es válido promediar sus resultados para pronosticar el desempeño en Juliaca. La contribución propuesta consiste en construir un corpus local con referencia humana y comparar dos pipelines sobre los mismos grupos de publicaciones, manteniendo prueba reservada. La representatividad y las clases difíciles deberán documentarse como límites, y la utilidad municipal seguirá siendo una posible aplicación posterior.


## E9. Referencias y trazabilidad

[Bibliografía P01–P15 y M01](../../literatura/referencias_ppi.md). Pendientes: extracción completa de varios artículos, verificación de rankings y ampliación de literatura reciente/local.

### Pregunta que orienta el estado del arte

¿Qué evidencia sobre clasificación de sentimientos en español, adaptación al lenguaje de redes y calidad de etiquetado permite diseñar una comparación de SVM y BETO para comentarios de servicios públicos? La selección debe incluir resultados que cuestionen la ventaja esperada de BETO, además de los favorables.

| Concepto | Palabras clave | Función |
|---|---|---|
| Tarea | sentiment classification, análisis de sentimientos, polarity | Delimitar la salida de clasificación. |
| Modelo | TF-IDF, support vector machine, SVM, BETO, Spanish BERT | Identificar comparadores y fundamentos. |
| Dominio | public services, waste collection, municipal, limpieza pública | Examinar transferibilidad al servicio. |
| Idioma y plataforma | Spanish, español, Facebook, social media, Peru | Identificar condiciones cercanas. |
| Calidad | annotation agreement, macro-F1, data leakage, domain adaptation | Sustentar controles metodológicos. |

La evidencia se interpreta en cuatro niveles: comparación directa de modelos (P05), clasificación cercana por idioma/plataforma (P04, P08, P12), aplicaciones ambientales (P09, P15) y fundamentos metodológicos. La cercanía temática no equivale a identidad de población o tarea. El registro de búsqueda conserva lo realmente consultado; no se atribuyen consultas a bases no utilizadas.

### Evidencias y revisión de entrega

[Índice de evidencias](evidencias/README.md) · [Rúbrica de la sesión](../../rubricas/U3_S03_rubrica.md).

La redacción se revisó para mantener correspondencia entre problema, objetivos, indicadores y procedimiento. La aprobación académica corresponde al docente; las actividades aún no ejecutadas permanecen identificadas.


# Desarrollo — U3 Sesión 4: Diseño de investigación

**Título:** Comparación de TF-IDF con SVM y BETO para clasificar sentimientos en comentarios ciudadanos sobre limpieza pública y recojo de residuos sólidos en Juliaca

**Autor:** Yoseth Orlando Llave Huachaca.

**Curso:** Investigación III, Ingeniería de Sistemas, Universidad Peruana Unión.

**Actualización:** 26 de noviembre de 2026.

**Estado:** propuesta metodológica redactada; no representa experimentos, recolección o validaciones ejecutados. El alcance de esta entrega es documental y prospectivo; la ejecución se realizará en una etapa futura.

## E1. Enfoque, alcance y tipo

Se propone un enfoque cuantitativo, alcance comparativo y tipo aplicado. El diseño es un experimento computacional pareado: dos pipelines predicen las etiquetas de los mismos comentarios reservados. No es un experimento causal sobre ciudadanos ni sobre el servicio municipal. El objetivo general y los OE son los de la sesión 2.

## E2. Diseño y protocolo experimental

Selección de publicaciones, anonimización, anotación individual, revisión de etiquetas, agrupamiento, partición, entrenamiento/validación, prueba reservada e interpretación. El esquema se incluye en [diagrama del método](evidencias/esquema_metodo.md).

| Componente | Configuración propuesta antes de observar prueba |
|---|---|
| SVM | TfidfVectorizer y LinearSVC en un pipeline; unigramas o unigramas+bigramas; C en {0.1,1,10}; class_weight en {None,balanced}; 12 configuraciones. |
| TF-IDF | min_df=2, max_df=1.0, sublinear_tf=True; vocabulario aprendido exclusivamente en entrenamiento. No eliminar negaciones. |
| BETO | dccuchile/bert-base-spanish-wwm-cased con cabeza de tres clases; tokenizador original; longitud 128 o 256; learning rate 2e-5 o 5e-5; 2 o 3 épocas; batch 8; AdamW, weight_decay=0.01; 8 configuraciones. |
| Selección | Mayor macro-F1 en validación; empate: menor complejidad/costo dentro de cada familia. Guardar todas las ejecuciones, incluso fallidas. |
| Semillas | 42 para partición y selección; 42,52,62 para reproducibilidad de la configuración elegida. No escoger la mejor semilla en prueba. |
| Entrada | Mismo texto anonimizado. SVM puede normalizar a minúsculas; BETO cased conserva mayúsculas. Diferencias explícitas forman parte del pipeline, no se atribuyen solo a arquitectura. |
| Recursos | Python, scikit-learn y Transformers/PyTorch. Registrar versiones, revisión del modelo, hardware y duración reales. El estudiante usará su computadora para el piloto y Google Colab para BETO; GPU, memoria, duración de sesión y presupuesto efectivo se comprobarán antes de entrenar. |

Estas configuraciones son propuestas replicables, no modelos entrenados. Si la memoria o el volumen obligan a cambios, registrar una enmienda antes de abrir prueba. La rejilla y esfuerzo de ajuste distintos limitan la interpretación; se documentará el número de intentos por familia.

OE1 corresponde al corpus; OE2 a los pipelines; OE3 a métricas y contraste; OE4 al análisis de errores y bitácora. No se añaden objetivos que midan rutas de recojo o satisfacción.

## E3. Población, muestra y selección

La población accesible serán comentarios públicos en español en publicaciones sobre limpieza pública y recojo en Juliaca de las cuatro fuentes propuestas. No se inferirá residencia del autor. La unidad textual será el comentario, anidado en su publicación; la fuente será otro nivel de agrupamiento.

Muestreo intencional de publicaciones pertinentes, con extracción consecutiva de comentarios elegibles en orden registrado. No seleccionar por cantidad de reacciones ni por polaridad. Registrar límites de acceso, comentarios no visibles y exclusiones. Incluir texto legible, relación explícita con servicio y Juliaca y fecha dentro de ventana. Excluir spam, duplicados, publicidad, otros lugares, solo imágenes y lengua no interpretable por el investigador. Las opiniones mixtas/ambiguas se conservarán aparte.

La ventana propuesta es noviembre 2024–octubre 2026, a confirmar mediante piloto. Meta logística preliminar: 600 comentarios etiquetables sin cuotas obligatorias por clase. No es un cálculo de potencia ni una garantía de suficiencia de BETO. No fabricar neutralidad ni balancear prueba artificialmente. Si no se alcanza, ampliar publicaciones elegibles y documentar cobertura antes de cambiar fechas; evaluar curvas de aprendizaje y precisión de intervalos durante la planificación antes de congelar tamaño.

Reservar aproximadamente 60 % entrenamiento, 20 % validación y 20 % prueba por grupos de publicaciones. Unir publicaciones vinculadas por duplicados o textos casi idénticos; ningún grupo cruzará particiones. Buscar distribución de clases compatible sin romper grupos y reportar proporciones efectivas. No modificar prueba para mejorar resultados. Si faltan clases o hay pocos grupos independientes, ampliar datos antes de ejecutar el contraste. El piloto se incorpora, si procede, únicamente al entrenamiento y se excluyen de prueba sus publicaciones completas.

## E4. Operacionalización

La [matriz vigente](../../ppi/02_matriz_operacionalizacion.md) define enfoque, macro-F1, métricas secundarias y controles. Cada predicción tendrá ID del comentario, etiqueta real, predicción, modelo, semilla y partición. Las etiquetas se revisarán sin ver predicciones.

## E5. Procedimiento y cronograma

| Semana relativa | Fase / entradas | Actividad | Salida | Responsable |
|---|---|---|---|---|
| 1 | Protocolo y fuentes | Revisar acceso, ética y recursos; localizar 30 publicaciones piloto. | Registro de viabilidad. | Investigador. |
| 2 | 100 comentarios piloto | Anotación individual y revisión diferida, acuerdo, revisión de etiquetas y ajuste de guía. | Informe piloto y guía versionada. | Investigador. |
| 3–4 | Fuentes confirmadas | Recolectar y etiquetar corpus definitivo. | Corpus anonimizado y exclusiones. | Investigador. |
| 5 | Corpus congelado | Agrupar, dividir y ajustar configuraciones. | Manifiesto y validación. | Investigador. |
| 6 | Configuraciones elegidas | Ejecutar evaluación reservada y semillas. | Predicciones y métricas. | Investigador. |
| 7 | Resultados | Contraste e interpretación de errores. | Informe comparativo. | Investigador. |
| 8 | Evidencias | Revisar reporte y reproducibilidad. | Entrega final. | Investigador. |

Son ocho semanas de futura ejecución individual, sin fechas de inicio comprometidas.

## E6. Plan de análisis y contraste

Reportar distribución de clases, matriz de confusión, macro-F1 y precisión/recall/F1 por clase. El contraste principal usa las ejecuciones predeclaradas con semilla 42; las otras semillas describen sensibilidad, sin tratar las mismas observaciones como nuevas muestras independientes.

H0: Δ=0; H1: Δ≠0. α=0,05. Se propone aleatorización pareada por grupo de publicación: intercambiar entre modelos, con probabilidad 0,5, todos los pares de predicciones del grupo, recalcular diferencia macro-F1 y repetir 10.000 veces con semilla fija. p=(1+número de diferencias absolutas al menos tan grandes como la observada)/(1+10.000). La validez depende de intercambiabilidad bajo la nula e independencia razonable entre grupos; revisarlas antes de inferir. El intercambio de predicciones exige una hipótesis de intercambiabilidad más fuerte que la mera igualdad de dos valores de macro-F1; el informe deberá declarar este supuesto y limitar la conclusión si no es defendible. No usar t de Student sobre dos puntajes únicos.

Obtener además intervalo percentil del 95 % para Δ con 10.000 remuestras y semilla 2026 mediante bootstrap pareado de grupos, conservando juntos comentarios y predicciones. Registrar replicaciones con clases ausentes; si son frecuentes o hay muy pocos grupos, no presentar el intervalo como estable: ampliar corpus o limitar el reporte a descriptivo. Estos intervalos son condicionales a los modelos entrenados y corpus accesible, no a toda la ciudad. Δ observado estima la diferencia de desempeño en el dominio accesible bajo este protocolo; el p-valor no convierte el muestreo intencional en probabilístico.

Rechazar H0 si p<0,05. La expectativa de BETO superior solo recibe apoyo si además Δ>0; si no, informar resultado contrario o evidencia insuficiente. Evaluar magnitud y errores junto al p-valor. Las métricas secundarias serán descriptivas, sin múltiples pruebas confirmatorias no planificadas. M01 orienta la selección del contraste; la adaptación por grupos es una decisión del protocolo que se revisará antes de la futura ejecución.

## E7. Amenazas y controles

| Validez | Amenaza | Control y límite residual |
|---|---|---|
| Interna | Fuga por duplicados, publicaciones y vocabulario. | Grupos conjuntos, deduplicación y TF-IDF solo en entrenamiento. |
| Constructo | Neutral confundido con mixto; ironía. | Guía explícita, un investigador con revisión diferida, revisión de etiquetas y categoría fuera de análisis. |
| Externa | Selección de páginas y acceso incompleto. | Reportar cobertura; no extrapolar a todos los ciudadanos. |
| Estadística | Pocos grupos, desbalance, semilla. | Intervalos agrupados, soporte y sensibilidad; ampliar datos si insuficientes. |
| Interna | Recursos de ajuste diferentes. | Rejillas y presupuestos transparentes; interpretar pipelines completos. |

## E8. Ética y riesgos

Antes de recolectar, revisar durante la planificación los requisitos institucionales, condiciones vigentes de acceso y permisos. Que un comentario sea visible no autoriza cualquier reutilización. No eludir controles ni extraer contenido privado. No registrar perfiles, nombres, fotos o IDs de usuarios. Enmascarar datos personales incluidos en el texto antes de análisis; almacenar vínculo a publicación solo en registro restringido. No subir comentarios reales al repositorio público. Para Google Colab se utilizará únicamente texto previamente desidentificado y con acceso autorizado; revisar durante la planificación las condiciones de tratamiento externo antes de cargar el corpus.

Riesgos principales: falta de acceso (alternativa: suspender esa fuente y documentarlo), pocos ejemplos neutrales (ampliar publicaciones sin forzar etiquetas), sesgo de etiquetado individual (documentar consistencia y limitaciones), memoria insuficiente (ensayo técnico y enmienda preprueba). No se fija retención legal ni se presume excepción de consentimiento; el plazo y responsable de custodia se aprobarán antes de recolección.

## E9. Procedimiento metodológico redactado y referencias

Se realizará una comparación cuantitativa de dos pipelines supervisados sobre un corpus de comentarios temáticos de Juliaca. Después de confirmar acceso y viabilidad, se aplicará anotación individual y se conservará una referencia humana revisada. Las publicaciones y duplicados se mantendrán separados entre particiones para reducir fuga de información. Los modelos se ajustarán en entrenamiento y validación; una prueba reservada permitirá estimar desempeño y diferencias pareadas. El reporte distinguirá precisión predictiva, incertidumbre, errores y límites de cobertura. El diseño no permite atribuir cambios al servicio municipal.

Referencias: P01–P03, P06–P08 y M01 en [bibliografía](../../literatura/referencias_ppi.md). Copia del procedimiento en `ppi/05_procedimiento_metodologico.md`. Pendientes: recursos, colaboradores, fecha inicial y aprobación del protocolo.

### Reglas de ejecución y cierre de fases

La recolección definitiva comenzará después de comprobar acceso y revisar el piloto. Antes de entrenar, se generará un manifiesto con grupos, clases y particiones. El archivo de prueba se reservará hasta elegir ambas configuraciones. El investigador no cambiará la muestra ni la definición de neutralidad para favorecer un resultado.

| Incidencia | Decisión prevista | Registro |
|---|---|---|
| Falta de alguna clase o de grupos suficientes | Ampliar la recolección antes de congelar prueba; revisar viabilidad si persiste. | Enmienda al protocolo y conteos reales. |
| GPU no disponible o memoria insuficiente | Posponer BETO o ajustar lote/longitud antes de la evaluación final. | Hardware efectivo, configuración y razón del cambio. |
| Interrupción de Colab | Recuperar el último estado íntegro; identificar reinicio y duración efectiva. | Ejecución marcada como interrumpida hasta completarse. |
| Acceso accidental a etiquetas de prueba durante ajuste | Declarar contaminación y definir una nueva prueba independiente, si es posible. | Incidencia y nueva versión del manifiesto. |
| Diferencia no significativa | Informar incertidumbre y tamaño de efecto; no afirmar equivalencia. | Informe comparativo. |

El criterio principal de selección será macro-F1 de validación. Para SVM, los empates se resolverán por unigramas, menor C y ausencia de ponderación, en ese orden; para BETO, por menor longitud, menos épocas y menor tasa de aprendizaje. Estas reglas propuestas evitan escoger retrospectivamente por prueba y deberán mantenerse al congelar el protocolo.

### Evidencias y revisión de entrega

[Índice de evidencias](evidencias/README.md) · [Rúbrica de la sesión](../../rubricas/U3_S04_rubrica.md).

La redacción se revisó para mantener correspondencia entre problema, objetivos, indicadores y procedimiento. La aprobación académica corresponde al docente; las actividades aún no ejecutadas permanecen identificadas.


# Desarrollo — U3 Sesión 5: Recolección de datos

**Título:** Comparación de TF-IDF con SVM y BETO para clasificar sentimientos en comentarios ciudadanos sobre limpieza pública y recojo de residuos sólidos en Juliaca

**Autor:** Yoseth Orlando Llave Huachaca.

**Curso:** Investigación III, Ingeniería de Sistemas, Universidad Peruana Unión.

**Actualización:** 26 de noviembre de 2026.

**Estado:** propuesta metodológica redactada; no representa experimentos, recolección o validaciones ejecutados. El alcance de esta entrega es documental y prospectivo; la ejecución se realizará en una etapa futura.

## E1. Técnicas de recolección

Se empleará análisis documental de comentarios digitales mediante observación de publicaciones públicas sobre limpieza pública y recojo de residuos sólidos en Juliaca. El muestreo será no probabilístico intencional: las publicaciones se seleccionarán por pertinencia temática, localidad y disponibilidad de acceso. Dentro de cada publicación se registrarán consecutivamente los comentarios elegibles, conservando el orden de revisión.

| Indicador | Técnica | Instrumento | Fuente |
|---|---|---|---|
| Pertinencia y cobertura | Observación documental | Registro de publicaciones y comentarios | Páginas institucionales y medios locales propuestos. |
| Sentimiento | Clasificación manual individual | Guía y ficha de revisión | Texto desidentificado de cada comentario. |
| Consistencia del etiquetado | Revisión diferida del mismo investigador | Ficha inicial y segunda revisión | Submuestra del corpus. |
| Macro-F1 y métricas por clase | Evaluación computacional futura | Predicciones y ficha experimental | Prueba reservada común. |
| Integridad y recursos | Registro técnico | Manifiesto, particiones y bitácora | Archivos y ejecuciones futuras. |

## E2. Instrumentos propuestos

Se utilizará una ficha estructurada en Excel o CSV para registrar código interno, fuente, fecha, temática y texto sin identificadores personales. La guía definirá positivo, negativo, neutral y no_clasificable. Las plantillas de [instrumentos](../../instrumentos/diccionario_datos.md) están preparadas sin datos reales. La recolección propuesta será manual; no se requiere construir ahora una aplicación ni un recolector automático.

## E3. Control de calidad previsto

El investigador comprobará la claridad de la guía mediante ejemplos y una revisión diferida. Se propone volver a etiquetar el 20 % del corpus, seleccionado aleatoriamente con semilla 42, después de al menos siete días y sin consultar las etiquetas iniciales. Se calculará el porcentaje de coincidencia y se examinarán los cambios por categoría. Este control mide consistencia intraevaluador; no demuestra acuerdo entre personas ni elimina el sesgo individual. No se solicitará validación por expertos como actividad de esta entrega.

## E4. Prueba preliminar futura

Se propone revisar entre 50 y 100 comentarios antes de la recolección definitiva. Se observarán accesibilidad, tiempo de registro, claridad de categorías y frecuencia de casos ambiguos. Las reglas se ajustarán antes de congelar el corpus. No se presentan resultados ni se afirma haber realizado el piloto. Véase el [plan](evidencias/piloto.md).

## E5. Cantidad y calendario propuestos

La meta inicial será de 600 comentarios elegibles, sin cuotas obligatorias por sentimiento. Es una estimación logística, no un cálculo de potencia. Si la cobertura o las clases son insuficientes, se revisará la viabilidad y el tamaño antes de entrenar. Se conservará la ventana preliminar noviembre de 2024–octubre de 2026 como propuesta, ajustable al comprobar acceso.

La ejecución se organizará en semanas relativas: semana 1, revisión de fuentes y reglas; semana 2, prueba preliminar; semanas 3–4, recolección manual; semana 5, revisión diferida y cierre del corpus; semanas 6–7, entrenamiento y comparación; semana 8, interpretación. Todas son actividades futuras a cargo de Yoseth Orlando Llave Huachaca. La computadora se utilizará para el registro y Google Colab para BETO, según disponibilidad de recursos.

## E6. Diccionario y almacenamiento

Los registros usarán UTF-8 e identificadores internos. Se separará el registro de enlaces del corpus desidentificado. El [diccionario](../../instrumentos/diccionario_datos.md) define campos y controles. Los comentarios reales se mantendrán fuera del repositorio público. Se documentarán versiones, conteos y particiones antes del experimento.

## E7. Limpieza y control de calidad

Se excluirán publicidad, duplicados, textos ajenos al tema y casos cuya localidad o periodo no puedan verificarse. Los textos mixtos o ambiguos se conservarán como no_clasificable, fuera de las tres clases del experimento principal, y se reportará su cantidad. Se preservarán negaciones y emojis relevantes. No se eliminarán casos por ser difíciles para el modelo ni se inventarán etiquetas para balancear clases.

## E8. Privacidad y acceso

Se utilizarán únicamente fuentes accesibles mediante una vía permitida, respetando sus condiciones de uso. Se omitirán nombres, perfiles, teléfonos y otros identificadores personales. El origen público no implica permiso automático de redistribución. Antes de transferir información a Colab se comprobará que el tratamiento externo sea admisible y que los textos estén desidentificados. Estas comprobaciones pertenecen a la futura ejecución.

## E9. Redacción y referencias

La recolección se plantea mediante análisis documental y registro manual estructurado de comentarios públicos pertinentes. El investigador aplicará una guía de clasificación y revisará una submuestra en un segundo momento. La cantidad definitiva dependerá de la viabilidad observada. Los datos servirán posteriormente para comparar ambos modelos bajo particiones comunes. P04, P05, P08, P12 y P13 aportan antecedentes y límites metodológicos; véase la [bibliografía](../../literatura/referencias_ppi.md).

Esta entrega presenta el diseño de técnicas e instrumentos. Los criterios de la rúbrica que solicitan validación o piloto ejecutados se presentan como planificación futura, conforme al alcance indicado por el estudiante; no se declaran cumplidos mediante resultados inexistentes.


# Referencias del PPI

Consulta de fuentes: 26 de noviembre de 2026. Los códigos P no corresponden a los R del corpus histórico.

**P01.** Pang, B., Lee, L. y Vaithyanathan, S. (2002). Thumbs up? Sentiment Classification using Machine Learning Techniques. EMNLP. [Fuente](https://aclanthology.org/W02-1011/).

**P02.** Devlin, J., Chang, M.-W., Lee, K. y Toutanova, K. (2019). BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding. NAACL. [Fuente](https://aclanthology.org/N19-1423/).

**P03.** Cañete, J. et al. (2020). Spanish Pre-Trained BERT Model and Evaluation Data. PML4DC, ICLR. [Fuente](https://huggingface.co/dccuchile/bert-base-spanish-wwm-cased).

**P04.** Adrianzén Torres, M. J. y Escobedo Cárdenas, E. J. (2021). Análisis comparativo de métodos de machine learning para clasificar opiniones sobre el servicio de restaurantes peruanos en Facebook. CIIS, 67–81. [Fuente](https://doi.org/10.26439/ciis2021.5578).

**P05.** Rosenbrock, G., Trossero, S. y Pascal, A. (2021). Técnicas de análisis de sentimientos aplicadas a la valoración de opiniones en el lenguaje español. CACIC, 291–300. [Fuente](https://sedici.unlp.edu.ar/handle/10915/130344).

**P06.** Areshey, A. y Mathkour, H. (2023). Transfer Learning for Sentiment Classification Using Bidirectional Encoder Representations from Transformers (BERT) Model. Sensors, 23, 5232. [Fuente](https://www.mdpi.com/1424-8220/23/11/5232).

**P07.** Talaat, A. S. (2023). Sentiment analysis classification system using hybrid BERT models. Journal of Big Data, 10, 110. [Fuente](https://doi.org/10.1186/s40537-023-00781-w).

**P08.** Barbieri, F., Espinosa Anke, L. y Camacho-Collados, J. (2022). XLM-T: Multilingual Language Models in Twitter for Sentiment Analysis and Beyond. LREC. [Fuente](https://aclanthology.org/2022.lrec-1.27/).

**P09.** Jenkins, E. L., Lukose, D., Brennan, L., Molenaar, A. y McCaffrey, T. A. (2023). Exploring Food Waste Conversations on Social Media: A Sentiment, Emotion, and Topic Analysis of Twitter Data. Sustainability, 15, 13788. [Fuente](https://www.mdpi.com/2071-1050/15/18/13788).

**P10.** Zhang, W., Deng, Y., Liu, B., Pan, S. y Bing, L. (2024). Sentiment Analysis in the Era of Large Language Models: A Reality Check. Findings of NAACL. [Fuente](https://aclanthology.org/2024.findings-naacl.246/).

**P11.** Zhang, W., Li, X., Deng, Y., Bing, L. y Lam, W. (2023). A Survey on Aspect-Based Sentiment Analysis: Tasks, Methods, and Challenges. IEEE TKDE. Versión de autores 2022. [Fuente](https://arxiv.org/abs/2203.01054).

**M01.** Dror, R., Baumer, G., Shlomov, S. y Reichart, R. (2018). The Hitchhiker’s Guide to Testing Statistical Significance in Natural Language Processing. ACL. [Fuente](https://aclanthology.org/P18-1128/).

**C01.** Municipalidad Provincial de San Román (2024). Resolución de Gerencia Municipal 039-2024-MPSR-J/GEMU. [Fuente institucional](https://www.gob.pe/institucion/munisanroman/normas-legales/5166408-039-2024-mpsr-j-gemu). Evidencia de intervención institucional sobre residuos; no mide satisfacción ciudadana.


**P12.** Pérez, J. M., Furman, D. A., Alonso Alemany, L. y Luque, F. M. (2022). RoBERTuito: a pre-trained language model for social media text in Spanish. LREC, 7235–7243. [Fuente](https://aclanthology.org/2022.lrec-1.785/).

**P13.** Rodríguez-Barroso, N., Martínez Cámara, E., Camacho Collados, J., Luzón, M. V. y Herrera, F. (2024). Federated Learning for Exploiting Annotators’ Disagreements in Natural Language Processing. Transactions of the Association for Computational Linguistics, 12, 630–648. [Fuente](https://aclanthology.org/2024.tacl-1.35/).

**P14.** Zhang, X., Mao, R. y Cambria, E. (2024). SenticVec: Toward Robust and Human-Centric Neurosymbolic Sentiment Analysis. Findings of ACL, 4851–4863. [Fuente](https://aclanthology.org/2024.findings-acl.289/).

**P15.** Sui, F. y Zhang, H. (2024). How to go green? Exploring public attention and sentiment towards waste sorting behaviors on Weibo platform: A study based on text co-occurrence networks and deep learning. Heliyon, 10(19), e38510. [Registro y resumen](https://pubmed.ncbi.nlm.nih.gov/39403487/). DOI: 10.1016/j.heliyon.2024.e38510.
