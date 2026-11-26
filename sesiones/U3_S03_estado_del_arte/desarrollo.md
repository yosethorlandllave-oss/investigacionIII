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
