# Problema y objetivos

Comparación de TF-IDF con SVM y BETO para clasificar sentimientos en comentarios ciudadanos sobre limpieza pública y recojo de residuos sólidos en Juliaca

¿Qué diferencias de macro-F1, precisión y recall presentan TF-IDF con SVM y BETO al clasificar sentimientos en comentarios ciudadanos sobre limpieza pública y recojo de residuos sólidos en Juliaca, utilizando los mismos datos etiquetados y particiones de evaluación?

Comparar el desempeño de TF-IDF con SVM y BETO en la clasificación de sentimientos de comentarios ciudadanos sobre limpieza pública y recojo de residuos sólidos en Juliaca, mediante una evaluación reproducible con métricas y particiones comunes.

| Código | Objetivo específico | Evidencia esperada |
|---|---|---|
| OE1 | Construir un corpus temático anonimizado y etiquetado mediante un protocolo de selección y anotación. | Registro de selección, guía, acuerdo y versión del corpus. |
| OE2 | Configurar y entrenar TF-IDF con SVM y ajustar BETO utilizando particiones compartidas sin fuga de información. | Configuración, manifiesto de particiones y modelos. |
| OE3 | Comparar macro-F1 y métricas por clase con estimaciones de incertidumbre bajo un protocolo predefinido. | Predicciones, métricas, diferencia y contraste. |
| OE4 | Analizar errores y limitaciones de transferencia y documentar la reproducibilidad del experimento. | Tipología de errores, ficha técnica e informe. |

La hipótesis de investigación propone que BETO obtendrá mayor macro-F1 que SVM; es una expectativa que debe contrastarse, no un resultado.

Sea Δ = macro-F1(BETO) − macro-F1(SVM) en el mismo conjunto de prueba. Para el contraste principal se plantea H0: Δ = 0 frente a H1: Δ ≠ 0. Se usa contraste bilateral para detectar también una ventaja de SVM. Solo una diferencia positiva con evidencia estadística apoyará la expectativa de superioridad de BETO. Un resultado no significativo no prueba igualdad. No se formulan hipótesis separadas para cada objetivo instrumental.

Desarrollo argumentado: [sesión 1](../sesiones/U3_S01_problema_justificacion/desarrollo.md).
