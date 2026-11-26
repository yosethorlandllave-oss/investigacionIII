# Matriz de operacionalización

| Variable | Definición conceptual y operacional | Dimensión / indicador | Escala | Instrumento |
|---|---|---|---|---|
| Independiente: enfoque de clasificación | Procedimiento que transforma texto en una clase. Dos niveles: pipeline TF-IDF–LinearSVC y BETO ajustado. | Identificador y configuración del modelo. | Nominal | Ficha experimental. |
| Dependiente principal: desempeño | Concordancia entre predicciones y etiquetas humanas adjudicadas. | Macro-F1: promedio no ponderado del F1 de positivo, negativo y neutral. | Numérica 0–1 | Predicciones y script de métricas. |
| Dependientes secundarias | Desempeño diferenciado por categoría. | Precision, recall y F1 por clase; exactitud y matriz de confusión. | 0–1 y recuentos | Informe de evaluación. |
| Control: datos | Mismos comentarios y etiquetas para ambos enfoques. | Hash de corpus, IDs y partición; tres clases fijas. | Nominal / recuentos | Manifiesto del corpus. |
| Control: selección de configuración | Ajuste sin acceso a prueba. | Rejilla, criterio de validación y presupuesto documentados. | Registro | Ficha experimental. |
| Calidad de anotación | Acuerdo independiente antes de adjudicar. | Kappa de Cohen, acuerdo porcentual y soporte por clase. | Kappa −1 a 1; proporciones | Fichas de dos anotadores. |
| Descriptiva: recursos | Condiciones de ejecución, no parte del título ni de la hipótesis principal. | Hardware, versiones, duración y semillas. | Texto / segundos | Bitácora. |
