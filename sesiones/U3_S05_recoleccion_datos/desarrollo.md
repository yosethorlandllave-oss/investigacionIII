# Desarrollo — U3 Sesión 5: Recolección de datos

**Título:** Comparación de TF-IDF con SVM y BETO para clasificar sentimientos en comentarios ciudadanos sobre limpieza pública y recojo de residuos sólidos en Juliaca

**Autor:** Yoseth Orlando Llave Huachaca.

**Curso:** Investigación III, Ingeniería de Sistemas, Universidad Peruana Unión.

**Actualización:** 26 de noviembre de 2026.

**Estado:** propuesta metodológica redactada; no representa experimentos, recolección o validaciones ejecutados. Las decisiones operativas propuestas requieren revisión del asesor.

## E1. Matriz indicador–técnica–instrumento–fuente

| Indicador | Técnica | Instrumento | Fuente / frecuencia |
|---|---|---|---|
| Elegibilidad, cobertura y exclusiones | Observación documental | registro_publicaciones.csv y registro_recoleccion.csv | Publicaciones propuestas; cada lote. |
| Etiquetas, acuerdo porcentual y kappa | Anotación independiente y adjudicación | guia_anotacion.md, anotacion_independiente.csv y adjudicacion.csv | Dos anotadores; piloto y corpus. |
| Macro-F1, precisión, recall, F1 por clase, exactitud y confusión | Evaluación computacional | predicciones.csv y script de métricas por implementar | Etiquetas y predicciones de prueba; cada ejecución predefinida. |
| Modelo y configuración seleccionada | Registro del experimento | ficha_experimento.csv | Cada configuración, validación y ejecución. |
| Hash, soporte, grupos y particiones comunes | Control del corpus | manifiesto_corpus.csv y particiones.csv | Cada versión congelada. |
| Hardware, versiones, semillas y duración | Bitácora técnica | ficha_experimento.csv | Computadora/Colab; cada ejecución. |
| Frecuencia de errores por fenómeno | Revisión cualitativa descriptiva | analisis_errores.csv | Errores de prueba, después de congelar resultados. |
| Reglas y afectados por limpieza | Auditoría de transformación | control_limpieza.csv | Cada lote y regla. |
| Acceso, custodia y condiciones | Revisión documental | condiciones_acceso.csv | Cada fuente antes de recopilar o transferir. |

La técnica es el procedimiento de obtención o medición; el instrumento organiza sus reglas y campos; Python o una hoja de cálculo son herramientas para aplicarlo.

## E2. Instrumentos elaborados

En `instrumentos/` se encuentran la guía de anotación, registro de publicaciones, registro de recolección, ficha de anotación independiente, adjudicación, diccionario, ficha experimental, esquema de predicciones y ficha de validación, manifiesto, particiones, control de limpieza, análisis de errores y condiciones de acceso. Todos tienen una finalidad y campos definidos. Los CSV contienen únicamente encabezados; no son evidencia de comentarios obtenidos.

## E3. Validación

Se propone revisar claridad y pertinencia de la guía con el asesor y, si se dispone, un especialista del servicio. Los participantes no están confirmados. Dos anotadores aplicarán la guía de forma independiente y se calculará acuerdo previo al consenso. El análisis de kappa se acompañará de frecuencias y desacuerdos porque depende de la prevalencia de clases.

Los instrumentos técnicos se validarán con comprobaciones de tipos, IDs, particiones disjuntas, ausencia de duplicados entre conjuntos y métricas sobre casos sintéticos. No corresponde alfa de Cronbach a fichas de captura o logs. Estado actual: instrumentos redactados; juicio de revisión, confiabilidad empírica y pruebas del software experimental pendientes. Véase `instrumentos/ficha_validacion.md`.

## E4. Piloto y ajustes

El [protocolo e informe pendiente](evidencias/piloto.md) define 30 publicaciones y hasta 100 comentarios, anotación doble y evaluación del tiempo, cobertura y acuerdo. No hay resultados reales disponibles en el repositorio. La versión posterior deberá registrar fecha, participantes, problemas observados y ajustes efectivos; no completar esos campos con resultados esperados.

## E5. Protocolo y calendario

Semana 1: confirmar acceso y condiciones, registrar páginas exactas y publicaciones. Semana 2: ejecutar piloto y revisar guía. Semanas 3–4: recolección y anotación definitivas. Las semanas son relativas al inicio aprobado y siguen S04; fechas exactas pendientes. Entorno confirmado por el estudiante: computadora para el piloto y Google Colab para BETO; comprobar GPU y condiciones de tratamiento antes de cargar datos.

Por cada lote: registrar fuente y orden de revisión; aplicar pertinencia; asignar ID; anonimizar; anotar por separado; calcular acuerdo; adjudicar; validar diccionario; versionar corpus y manifiesto. Documentar cada exclusión y cambio. El investigador custodia el registro; el segundo anotador y revisor se designarán antes del piloto.

## E6. Diccionario y almacenamiento

El [diccionario](../../instrumentos/diccionario_datos.md) define campos, valores permitidos y relación con variables. Guardar CSV UTF-8 restringido fuera de Git. Separar enlaces de publicaciones del texto anonimizado. Registrar hashes y conteos por versión; la misma versión debe alimentar ambos modelos. Los formularios públicos serán copias vacías.

## E7. Limpieza y calidad

| Problema | Detección | Tratamiento |
|---|---|---|
| Texto vacío | Nulo, solo espacios o sin contenido textual interpretable | Excluir con motivo. |
| Fechas o localidad inciertas | Registro no verificable | No presumir elegibilidad; revisar o excluir. |
| Duplicados exactos | Normalización Unicode/espacios y hash restringido | Conservar una instancia y trazabilidad del conteo. |
| Duplicados cercanos o republicaciones | Comparación textual y revisión manual previa a partición | Agrupar publicaciones relacionadas; documentar decisión. |
| Datos personales | Revisión del texto y patrones de teléfonos/correos | Enmascarar antes de distribuir o entrenar. |
| Etiquetas incompatibles | Validar conjunto de valores y desacuerdos | Adjudicar con guía; nunca completar automáticamente con predicción. |
| Longitudes extremas | Medir distribución en entrenamiento | Registrar truncamiento BETO; no excluir por desacuerdo con el modelo. |
| Desbalance | Conteos por clase/fuente | Informar; ponderación solo en entrenamiento y ajuste por validación. |

Preservar negación y emojis relevantes. Registrar regla, versión y número de afectados en cada transformación. No adaptar limpieza a errores de prueba después de observar el resultado final.

## E8. Ética, privacidad y acceso

El origen público se documentará, pero no se considerará permiso automático para extraer o redistribuir. El asesor revisará condiciones de plataforma y requisitos institucionales antes de recolectar; cualquier autorización necesaria debe quedar registrada. No habrá acceso a grupos privados, perfiles ni evasión de controles. La fuente se suspenderá si no se cuenta con una vía admisible.

No publicar nombres, imágenes, identificadores, URLs a comentarios individuales ni textos que permitan identificar usuarios. El acceso al corpus se limitará a personas designadas; la retención y eliminación se establecerán antes de captura. Tampoco se publicarán muestras textuales reales como ejemplos sin revisión específica. La caracterización de usuarios no es un objetivo del proyecto.

## E9. Redacción de la sección y referencias

La recolección se realizará mediante observación documental de publicaciones públicas pertinentes y un registro estructurado. Los comentarios pasarán por anonimización, revisión temática y anotación independiente. La referencia final procederá de adjudicación humana y se conservará junto con la versión de las reglas. La validación de instrumentos combinará revisión de contenido, acuerdo entre evaluadores y comprobaciones técnicas. Antes de la recolección definitiva se ejecutará un piloto que permita ajustar cobertura, ventana, tiempos y procedimientos. El protocolo mantendrá separados los datos restringidos y los artefactos públicos de reproducibilidad.

P04–P05 y P08–P09 aportan antecedentes de comentarios digitales; M01 orienta el reporte de evaluación. Véase [bibliografía](../../literatura/referencias_ppi.md). Esta sección se guarda también en `ppi/06_tecnicas_instrumentos.md`.

**Estado de rúbrica:** E1, E2, E5, E6, E7 y E9 redactados como propuesta. E3 y E4 requieren ejecución real; E8 requiere comprobar condiciones y responsabilidades antes de acceso. No se declara puntaje ni aprobación docente.

### Protocolo operativo por lote

1. Yoseth registrará fuente, fecha, vía de acceso y orden de revisión. Verificará localidad, periodo y relación con el servicio antes de interpretar sentimiento.
2. Asignará identificadores internos y enmascarará datos personales. Conservará las exclusiones con motivo; no guardará perfiles de usuarios.
3. Entregará copias independientes a dos anotadores. Cada persona registrará etiqueta, motivo y versión de guía sin ver la respuesta de la otra.
4. Calculará acuerdo antes del consenso, incluyendo no_clasificable. Luego documentará adjudicación y motivos; no utilizará predicciones como etiquetas humanas.
5. Verificará claves, duplicados, faltantes y consistencia. Los datos incompletos quedarán en revisión y no ingresarán al corpus congelado.
6. Cerrará el lote con conteos agregados, versión, incidencias y reglas aplicadas. Solo después se incorporará al manifiesto de particiones.

### Decisiones del piloto

La meta inicial es revisar hasta 100 comentarios de las publicaciones propuestas. Se registrarán tiempo efectivo, accesibilidad, distribución de etiquetas, porcentaje de exclusiones y acuerdo. Si kappa es menor que 0,70, se revisarán desacuerdos y ejemplos y se realizará una nueva ronda independiente; alcanzar esa meta no demuestra por sí solo validez. Si alguna clase es escasa, se ampliará cobertura por publicaciones, sin buscar o fabricar opiniones de una polaridad concreta. El paso al corpus definitivo requiere una guía estable y recursos suficientes, con revisión del asesor.

El segundo anotador, los comentarios efectivamente disponibles y las fechas siguen sin confirmarse. No se consideran resultados los ejemplos inventados de la guía ni las plantillas vacías. La revisión de contenido del asesor y la aplicación del piloto se documentarán cuando ocurran.

### Evidencias y revisión de entrega

[Índice de evidencias](evidencias/README.md) · [Rúbrica de la sesión](../../rubricas/U3_S05_rubrica.md).

La redacción se revisó para mantener correspondencia entre problema, objetivos, indicadores y procedimiento. La aprobación académica corresponde al docente; las actividades aún no ejecutadas permanecen identificadas.
