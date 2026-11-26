# Diccionario y almacenamiento

Todos los CSV usarán UTF-8. Una fila corresponde a una observación. Los archivos plantilla están vacíos: no acreditan recolección.

| Campo | Tipo / valores | Obligatorio | Función |
|---|---|---|---|
| comentario_id | Cadena aleatoria interna | Sí | Vincular anotación y predicción sin ID de plataforma. |
| publicacion_id | Código interno | Sí | Agrupación contra fuga. |
| grupo_id | Código de publicaciones conectadas por duplicados | Antes de dividir | Unidad de partición y remuestreo. |
| fuente | municipalidad, pachamama, decana, onda_azul | Sí | Cobertura. |
| fecha_comentario | ISO AAAA-MM-DD o no_disponible | Sí | Elegibilidad; excluir fecha desconocida sin evidencia alternativa. |
| texto_anonimizado | Texto | Sí | Entrada. Almacenamiento restringido. |
| tema | recojo, limpieza, acumulacion, general; separador ; | Sí | Pertinencia. |
| pertinente | si/no | Sí | Selección. |
| motivo_exclusion | Código o vacío si incluido | Condicional | Trazabilidad. |
| etiqueta_inicial / etiqueta_revision | positivo/negativo/neutral/no_clasificable | Antes de revisar | Coincidencia entre revisiones. |
| etiqueta_final | Mismos valores | Sí en corpus final | Referencia revisada. |
| motivo_adjudicacion | Texto sin datos personales | Si desacuerdo | Trazabilidad. |
| version_guia | Cadena | Sí | Reproducibilidad. |
| particion | piloto/train/validation/test/excluido | Al congelar | Control experimental. |

Separar registro restringido de URLs de publicaciones y condiciones de acceso del corpus anonimizado. No almacenar identificadores de usuarios. El texto puede seguir siendo localizable por buscadores; anonimización no justifica publicarlo automáticamente. Mantener datos reales fuera del repositorio y copias cifradas con acceso limitado. Definir responsable, retención y eliminación durante la planificación antes de recolectar. Git solo contendrá esquemas, código y métricas agregadas sin celdas que permitan identificar personas.

Predicciones: comentario_id, grupo_id, etiqueta_real, etiqueta_predicha, modelo, semilla, particion. Manifestar hashes, conteos y versión sin publicar textos. No agregar timestamps como datos ficticios a los formularios pendientes.


## Campos complementarios de las plantillas

| Campos | Tipo / regla | Archivo y relación |
|---|---|---|
| anotador_codigo, revisor_codigo, responsable_codigo | Código interno, sin nombre público; obligatorio al ejecutar. | Anotación, errores y limpieza. |
| etiqueta, etiqueta_real, etiqueta_predicha | Anotación admite cuatro valores; predicción principal admite positivo/negativo/neutral. | Anotación y predicciones. |
| motivo, observacion_anonimizada | Texto breve; no incluir datos identificables. | Razones de anotación y errores. |
| fecha_publicacion, fecha_revision, fecha, fecha_congelacion | ISO AAAA-MM-DD; vacíos hasta ejecutar. | Cronología. |
| fecha_captura, orden_revision | Fecha ISO y entero positivo, consecutivo dentro del lote de publicaciones o de la publicación para comentarios. | Registrar orden visible y limitaciones de plataforma sin afirmar exhaustividad. |
| url_restringida | URL a publicación; solo en registro restringido. | Publicaciones, nunca ID de usuario. |
| acceso_permitido, uso_permitido, redistribucion_permitida | si/no/pendiente; se exige si para la acción correspondiente. | Publicaciones y condiciones. |
| criterio_juliaca | Evidencia textual del vínculo geográfico sin identificar personas. | Publicaciones. |
| comentarios_visibles, comentarios_elegibles | Entero no negativo; no confundir visible con total real de plataforma. | Publicaciones. |
| ejecucion_id, lote_id | Cadena única interna. | Ejecuciones y limpieza. |
| modelo | svm_tfidf/beto; registrar arquitectura aparte en configuración. | Ejecución, predicción, errores. |
| revision_modelo | Commit/revisión del modelo descargado, o no_aplica para SVM. | Experimento. |
| hash_corpus, hash_particiones | SHA-256 de archivos congelados; no publicar textos. | Manifiesto y experimento. |
| configuracion, versiones, hardware | JSON o texto estructurado entre comillas CSV. | Hiperparámetros, dependencias y equipo real. |
| semilla, semilla_particion | Entero; valores predeclarados. | Experimento y particiones. |
| inicio, duracion_segundos | ISO con zona horaria; segundos no negativos. | Recursos reales de cada ejecución. |
| estado | pendiente/completado/fallido; para acceso pendiente/aprobado/rechazado. | Distinguir ejecución de plan. |
| origen_piloto | si/no; si implica train o excluido, nunca test/validation. | Particiones. |
| version_corpus | Cadena, p. ej. v1; vacía hasta congelación real. | Manifiesto y particiones. |
| n_comentarios, n_publicaciones, n_grupos | Enteros no negativos; unidades distintas. | Manifiesto. |
| n_train, n_validation, n_test | Enteros; su suma coincide con corpus principal. | Manifiesto. |
| n_positivo, n_negativo, n_neutral | Conteos del corpus principal; suma igual a n_comentarios. | Manifiesto. |
| n_excluido | Conteo fuera del corpus principal; no sumarlo otra vez a n_comentarios. | Manifiesto. |
| regla, version_regla, accion | Código y descripción del tratamiento aplicado. | Limpieza. |
| n_revisados, n_afectados | Enteros, afectados no mayor que revisados. | Limpieza. |
| tipo_error, contexto_necesario | negacion/ironia/mixto/lexico_local/contexto/otro; si/no. | Análisis de errores, criterios propuestos. |
| documento_condiciones, via_acceso | Referencia y modo autorizado de acceso. | Condiciones; pendiente hasta revisión. |
| consentimiento_o_fundamento, revision_institucional | Registro de decisión real y evidencia; no presumir exención. | Condiciones. |
| custodio, retencion, eliminacion | Responsable y reglas acordadas, sin datos privados en Git. | Condiciones. |

## Integridad y faltantes

Los CSV de recolección, revisión de etiquetas y particiones se relacionan mediante comentario_id; la publicación mediante publicacion_id. Una observación no puede pertenecer a dos grupos. Cada comentario tiene una fila por revisión y una etiqueta final. Una predicción es única por comentario/modelo/semilla. El manifiesto define n_comentarios como los casos de las tres clases incluidos en train/validation/test; los no clasificables se cuentan por separado.

Un dato desconocido permanece vacío o como pendiente solo durante planificación. Antes de congelar corpus, no se admiten IDs, textos, grupos, etiquetas ni particiones ausentes. No imputar sentimiento ni fechas con valores inventados. El diccionario admite piloto como fase de captura, pero el manifiesto final usa únicamente train/validation/test/excluido y conserva origen_piloto.
