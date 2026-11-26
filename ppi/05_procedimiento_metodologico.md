# Procedimiento metodológico

## E1. Enfoque, alcance y tipo

Se propone un enfoque cuantitativo, alcance comparativo y tipo aplicado. El diseño es un experimento computacional pareado: dos pipelines predicen las etiquetas de los mismos comentarios reservados. No es un experimento causal sobre ciudadanos ni sobre el servicio municipal. El objetivo general y los OE son los de la sesión 2.

## E2. Diseño y protocolo experimental

Selección de publicaciones, anonimización, anotación independiente, adjudicación, agrupamiento, partición, entrenamiento/validación, prueba reservada e interpretación. El esquema se incluye en [diagrama del método](../sesiones/U3_S04_diseno_investigacion/evidencias/esquema_metodo.md).

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

Muestreo intencional de publicaciones pertinentes, con extracción consecutiva de comentarios elegibles en orden registrado. No seleccionar por cantidad de reacciones ni por polaridad. Registrar límites de acceso, comentarios no visibles y exclusiones. Incluir texto legible, relación explícita con servicio y Juliaca y fecha dentro de ventana. Excluir spam, duplicados, publicidad, otros lugares, solo imágenes y lengua no interpretable por anotadores. Las opiniones mixtas/ambiguas se conservarán aparte.

La ventana propuesta es noviembre 2024–octubre 2026, a confirmar mediante piloto. Meta logística preliminar: 600 comentarios etiquetables y al menos 150 por cada una de las tres clases. No es un cálculo de potencia ni una garantía de suficiencia de BETO. No fabricar neutralidad ni balancear prueba artificialmente. Si no se alcanza, ampliar publicaciones elegibles y documentar cobertura antes de cambiar fechas; evaluar curvas de aprendizaje y precisión de intervalos con asesor antes de congelar tamaño.

Reservar aproximadamente 60 % entrenamiento, 20 % validación y 20 % prueba por grupos de publicaciones. Unir publicaciones vinculadas por duplicados o textos casi idénticos; ningún grupo cruzará particiones. Buscar distribución de clases compatible sin romper grupos y reportar proporciones efectivas. No modificar prueba para mejorar resultados. Si faltan clases o hay pocos grupos independientes, ampliar datos antes de ejecutar el contraste. El piloto se incorpora, si procede, únicamente al entrenamiento y se excluyen de prueba sus publicaciones completas.

## E4. Operacionalización

La [matriz vigente](02_matriz_operacionalizacion.md) define enfoque, macro-F1, métricas secundarias y controles. Cada predicción tendrá ID del comentario, etiqueta real, predicción, modelo, semilla y partición. Las etiquetas se adjudicarán sin ver predicciones.

## E5. Procedimiento y cronograma

| Semana relativa | Fase / entradas | Actividad | Salida | Responsable |
|---|---|---|---|---|
| 1 | Protocolo y fuentes | Revisar acceso, ética y recursos; localizar 30 publicaciones piloto. | Registro de viabilidad. | Investigador y asesor. |
| 2 | 100 comentarios piloto | Anotación doble, acuerdo, adjudicación y ajuste de guía. | Informe piloto y guía versionada. | Dos anotadores por confirmar. |
| 3–4 | Fuentes confirmadas | Recolectar y etiquetar corpus definitivo. | Corpus anonimizado y exclusiones. | Investigador y segundo anotador. |
| 5 | Corpus congelado | Agrupar, dividir y ajustar configuraciones. | Manifiesto y validación. | Investigador. |
| 6 | Configuraciones elegidas | Ejecutar evaluación reservada y semillas. | Predicciones y métricas. | Investigador. |
| 7 | Resultados | Contraste e interpretación de errores. | Informe comparativo. | Investigador con revisión del asesor. |
| 8 | Evidencias | Revisar reporte y reproducibilidad. | Entrega final. | Investigador. |

Son ocho semanas propuestas desde aprobación y disponibilidad de recursos; no constituyen fechas pactadas. No se declara que otro colaborador haya aceptado participar.

## E6. Plan de análisis y contraste

Reportar distribución de clases, matriz de confusión, macro-F1 y precisión/recall/F1 por clase. El contraste principal usa las ejecuciones predeclaradas con semilla 42; las otras semillas describen sensibilidad, sin tratar las mismas observaciones como nuevas muestras independientes.

H0: Δ=0; H1: Δ≠0. α=0,05. Se propone aleatorización pareada por grupo de publicación: intercambiar entre modelos, con probabilidad 0,5, todos los pares de predicciones del grupo, recalcular diferencia macro-F1 y repetir 10.000 veces con semilla fija. p=(1+número de diferencias absolutas al menos tan grandes como la observada)/(1+10.000). La validez depende de intercambiabilidad bajo la nula e independencia razonable entre grupos; revisarlas antes de inferir. El intercambio de predicciones exige una hipótesis de intercambiabilidad más fuerte que la mera igualdad de dos valores de macro-F1; el informe deberá declarar este supuesto y limitar la conclusión si no es defendible. No usar t de Student sobre dos puntajes únicos.

Obtener además intervalo percentil del 95 % para Δ con 10.000 remuestras y semilla 2026 mediante bootstrap pareado de grupos, conservando juntos comentarios y predicciones. Registrar replicaciones con clases ausentes; si son frecuentes o hay muy pocos grupos, no presentar el intervalo como estable: ampliar corpus o limitar el reporte a descriptivo. Estos intervalos son condicionales a los modelos entrenados y corpus accesible, no a toda la ciudad. Δ observado estima la diferencia de desempeño en el dominio accesible bajo este protocolo; el p-valor no convierte el muestreo intencional en probabilístico.

Rechazar H0 si p<0,05. La expectativa de BETO superior solo recibe apoyo si además Δ>0; si no, informar resultado contrario o evidencia insuficiente. Evaluar magnitud y errores junto al p-valor. Las métricas secundarias serán descriptivas, sin múltiples pruebas confirmatorias no planificadas. M01 orienta la selección del contraste; la adaptación por grupos es una decisión del protocolo que requiere revisión estadística del asesor.

## E7. Amenazas y controles

| Validez | Amenaza | Control y límite residual |
|---|---|---|
| Interna | Fuga por duplicados, publicaciones y vocabulario. | Grupos conjuntos, deduplicación y TF-IDF solo en entrenamiento. |
| Constructo | Neutral confundido con mixto; ironía. | Guía explícita, dos anotadores, adjudicación y categoría fuera de análisis. |
| Externa | Selección de páginas y acceso incompleto. | Reportar cobertura; no extrapolar a todos los ciudadanos. |
| Estadística | Pocos grupos, desbalance, semilla. | Intervalos agrupados, soporte y sensibilidad; ampliar datos si insuficientes. |
| Interna | Recursos de ajuste diferentes. | Rejillas y presupuestos transparentes; interpretar pipelines completos. |

## E8. Ética y riesgos

Antes de recolectar, revisar con asesor los requisitos institucionales, condiciones vigentes de acceso y permisos. Que un comentario sea visible no autoriza cualquier reutilización. No eludir controles ni extraer contenido privado. No registrar perfiles, nombres, fotos o IDs de usuarios. Enmascarar datos personales incluidos en el texto antes de análisis; almacenar vínculo a publicación solo en registro restringido. No subir comentarios reales al repositorio público. Para Google Colab se utilizará únicamente texto previamente desidentificado y con acceso autorizado; revisar con asesor las condiciones de tratamiento externo antes de cargar el corpus.

Riesgos principales: falta de acceso (alternativa: suspender esa fuente y documentarlo), pocos ejemplos neutrales (ampliar publicaciones sin forzar etiquetas), falta de segundo anotador (no declarar validación), memoria insuficiente (ensayo técnico y enmienda preprueba). No se fija retención legal ni se presume excepción de consentimiento; el plazo y responsable de custodia se aprobarán antes de recolección.

## E9. Procedimiento metodológico redactado y referencias

Se realizará una comparación cuantitativa de dos pipelines supervisados sobre un corpus de comentarios temáticos de Juliaca. Después de confirmar acceso y viabilidad, se aplicará anotación independiente y se conservará una referencia humana adjudicada. Las publicaciones y duplicados se mantendrán separados entre particiones para reducir fuga de información. Los modelos se ajustarán en entrenamiento y validación; una prueba reservada permitirá estimar desempeño y diferencias pareadas. El reporte distinguirá precisión predictiva, incertidumbre, errores y límites de cobertura. El diseño no permite atribuir cambios al servicio municipal.

Referencias: P01–P03, P06–P08 y M01 en [bibliografía](../literatura/referencias_ppi.md). Copia del procedimiento en `ppi/05_procedimiento_metodologico.md`. Pendientes: recursos, colaboradores, fecha inicial y aprobación del protocolo.
