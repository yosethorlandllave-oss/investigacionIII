# Desarrollo — U3 Sesión 1: Problema y justificación

**Título:** Comparación de TF-IDF con SVM y BETO para clasificar sentimientos en comentarios ciudadanos sobre limpieza pública y recojo de residuos sólidos en Juliaca

**Autor:** Yoseth Orlando Llave Huachaca.

**Curso:** Investigación III, Ingeniería de Sistemas, Universidad Peruana Unión.

**Actualización:** 26 de noviembre de 2026.

**Estado:** propuesta metodológica redactada; no representa experimentos, recolección o validaciones ejecutados. Las decisiones operativas propuestas requieren revisión del asesor.

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
