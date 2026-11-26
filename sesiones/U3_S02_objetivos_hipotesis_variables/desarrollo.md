# Desarrollo — U3 Sesión 2: Objetivos, hipótesis y variables

**Título:** Comparación de TF-IDF con SVM y BETO para clasificar sentimientos en comentarios ciudadanos sobre limpieza pública y recojo de residuos sólidos en Juliaca

**Autor:** Yoseth Orlando Llave Huachaca.

**Curso:** Investigación III, Ingeniería de Sistemas, Universidad Peruana Unión.

**Actualización:** 26 de noviembre de 2026.

**Estado:** propuesta metodológica redactada; no representa experimentos, recolección o validaciones ejecutados. Las decisiones operativas propuestas requieren revisión del asesor.

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
| Dependiente principal: desempeño | Concordancia entre predicciones y etiquetas humanas adjudicadas. | Macro-F1: promedio no ponderado del F1 de positivo, negativo y neutral. | Numérica 0–1 | Predicciones y script de métricas. |
| Dependientes secundarias | Desempeño diferenciado por categoría. | Precision, recall y F1 por clase; exactitud y matriz de confusión. | 0–1 y recuentos | Informe de evaluación. |
| Control: datos | Mismos comentarios y etiquetas para ambos enfoques. | Hash de corpus, IDs y partición; tres clases fijas. | Nominal / recuentos | Manifiesto del corpus. |
| Control: selección de configuración | Ajuste sin acceso a prueba. | Rejilla, criterio de validación y presupuesto documentados. | Registro | Ficha experimental. |
| Calidad de anotación | Acuerdo independiente antes de adjudicar. | Kappa de Cohen, acuerdo porcentual y soporte por clase. | Kappa −1 a 1; proporciones | Fichas de dos anotadores. |
| Descriptiva: recursos | Condiciones de ejecución, no parte del título ni de la hipótesis principal. | Hardware, versiones, duración y semillas. | Texto / segundos | Bitácora. |

Un corpus es un conjunto organizado de textos. Un pipeline encadena preparación y clasificación; la fuga de información ocurre cuando el ajuste utiliza datos reservados para evaluar. En cada clase, TP son aciertos positivos, FP falsas asignaciones y FN casos de la clase que el modelo omitió. Precisión mide cuántas asignaciones fueron correctas; recall, qué proporción de casos de la clase fue recuperada. F1 combina ambas medidas.

Para cada clase, precisión = TP/(TP+FP), recall = TP/(TP+FN) y F1 = 2TP/(2TP+FP+FN). Macro-F1 es el promedio de los tres F1. Se declarará zero_division=0 para cálculos indefinidos y se reportará soporte; una clase ausente en prueba obliga a revisar el diseño, no a celebrar un promedio incompleto.

## E7. Matriz de consistencia

| Problema | Objetivo | Hipótesis | Variable / indicador | Procedimiento y evidencia |
|---|---|---|---|---|
| Desempeño local no establecido en los antecedentes consultados. | Objetivo general: comparar SVM y BETO. | H0: Δ=0; H1: Δ≠0. Expectativa: Δ>0. | Enfoque; macro-F1. | Prueba común reservada y comparación pareada. |
| No existe aún un corpus local documentado en este repositorio. | OE1: construir corpus. | No requiere hipótesis independiente. | Acuerdo, soporte, elegibilidad. | Selección, anotación doble y adjudicación. |
| Comparaciones pueden confundir datos y arquitectura. | OE2: entrenar bajo protocolo común. | Se integra al contraste general. | Configuración y partición. | Ajuste solo en entrenamiento/validación. |
| Diferencias puntuales pueden ser inestables. | OE3: evaluar e inferir. | Contraste principal general. | Δ y variabilidad. | Remuestreo agrupado y contraste descrito en S04. |
| Promedios ocultan fallos del lenguaje local. | OE4: analizar errores. | Descriptivo, sin nuevas hipótesis confirmatorias. | Errores por clase y fenómeno. | Revisión ciega de casos anonimizados. |

## E8. Referencias y trazabilidad

P01–P03 fundamentan los enfoques; P04–P08 contextualizan la comparación y M01 orienta la inferencia. Véase [bibliografía](../../literatura/referencias_ppi.md). Copias para el PPI: [operacionalización](../../ppi/02_matriz_operacionalizacion.md) y [consistencia](../../ppi/03_matriz_consistencia.md).
