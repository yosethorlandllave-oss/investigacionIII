# Técnicas e instrumentos de recolección

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

Se utilizará una ficha estructurada en Excel o CSV para registrar código interno, fuente, fecha, temática y texto sin identificadores personales. La guía definirá positivo, negativo, neutral y no_clasificable. Las plantillas de [instrumentos](../instrumentos/diccionario_datos.md) están preparadas sin datos reales. La recolección propuesta será manual; no se requiere construir ahora una aplicación ni un recolector automático.

## E3. Control de calidad previsto

El investigador comprobará la claridad de la guía mediante ejemplos y una revisión diferida. Se propone volver a etiquetar el 20 % del corpus, seleccionado aleatoriamente con semilla 42, después de al menos siete días y sin consultar las etiquetas iniciales. Se calculará el porcentaje de coincidencia y se examinarán los cambios por categoría. Este control mide consistencia intraevaluador; no demuestra acuerdo entre personas ni elimina el sesgo individual. No se solicitará validación por expertos como actividad de esta entrega.

## E4. Prueba preliminar futura

Se propone revisar entre 50 y 100 comentarios antes de la recolección definitiva. Se observarán accesibilidad, tiempo de registro, claridad de categorías y frecuencia de casos ambiguos. Las reglas se ajustarán antes de congelar el corpus. No se presentan resultados ni se afirma haber realizado el piloto. Véase el [plan](../sesiones/U3_S05_recoleccion_datos/evidencias/piloto.md).

## E5. Cantidad y calendario propuestos

La meta inicial será de 600 comentarios elegibles, sin cuotas obligatorias por sentimiento. Es una estimación logística, no un cálculo de potencia. Si la cobertura o las clases son insuficientes, se revisará la viabilidad y el tamaño antes de entrenar. Se conservará la ventana preliminar noviembre de 2024–octubre de 2026 como propuesta, ajustable al comprobar acceso.

La ejecución se organizará en semanas relativas: semana 1, revisión de fuentes y reglas; semana 2, prueba preliminar; semanas 3–4, recolección manual; semana 5, revisión diferida y cierre del corpus; semanas 6–7, entrenamiento y comparación; semana 8, interpretación. Todas son actividades futuras a cargo de Yoseth Orlando Llave Huachaca. La computadora se utilizará para el registro y Google Colab para BETO, según disponibilidad de recursos.

## E6. Diccionario y almacenamiento

Los registros usarán UTF-8 e identificadores internos. Se separará el registro de enlaces del corpus desidentificado. El [diccionario](../instrumentos/diccionario_datos.md) define campos y controles. Los comentarios reales se mantendrán fuera del repositorio público. Se documentarán versiones, conteos y particiones antes del experimento.

## E7. Limpieza y control de calidad

Se excluirán publicidad, duplicados, textos ajenos al tema y casos cuya localidad o periodo no puedan verificarse. Los textos mixtos o ambiguos se conservarán como no_clasificable, fuera de las tres clases del experimento principal, y se reportará su cantidad. Se preservarán negaciones y emojis relevantes. No se eliminarán casos por ser difíciles para el modelo ni se inventarán etiquetas para balancear clases.

## E8. Privacidad y acceso

Se utilizarán únicamente fuentes accesibles mediante una vía permitida, respetando sus condiciones de uso. Se omitirán nombres, perfiles, teléfonos y otros identificadores personales. El origen público no implica permiso automático de redistribución. Antes de transferir información a Colab se comprobará que el tratamiento externo sea admisible y que los textos estén desidentificados. Estas comprobaciones pertenecen a la futura ejecución.

## E9. Redacción y referencias

La recolección se plantea mediante análisis documental y registro manual estructurado de comentarios públicos pertinentes. El investigador aplicará una guía de clasificación y revisará una submuestra en un segundo momento. La cantidad definitiva dependerá de la viabilidad observada. Los datos servirán posteriormente para comparar ambos modelos bajo particiones comunes. P04, P05, P08, P12 y P13 aportan antecedentes y límites metodológicos; véase la [bibliografía](../literatura/referencias_ppi.md).

Esta entrega presenta el diseño de técnicas e instrumentos. Los criterios de la rúbrica que solicitan validación o piloto ejecutados se presentan como planificación futura, conforme al alcance indicado por el estudiante; no se declaran cumplidos mediante resultados inexistentes.
