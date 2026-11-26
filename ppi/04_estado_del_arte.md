# Introducción y estado del arte

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



[Bibliografía](../literatura/referencias_ppi.md).
