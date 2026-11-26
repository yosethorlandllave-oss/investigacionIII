# Registro de búsqueda y selección del PPI

Fecha real de consulta: 26 de noviembre de 2026. Modalidad: búsqueda web dirigida y consulta de fuentes primarias; no se declara ejecución de consultas nativas en Scopus o Web of Science. Punto de partida: Word y texto LaTeX proporcionados por el estudiante.

## Consultas ejecutadas

- `"How to go green" "waste" Weibo 2024`
- `"10.26439/ciis2021.5578"`
- `"10915/130344" BETO`
- `"Exploring food waste conversations" 13788`
- `site.aclanthology.org sentiment analysis survey Zhang 2023 aspect`
- `site.gob.pe munisanroman limpieza residuos 2024 039`
- `site.aclanthology.org 2018 significance tests NLP Dror`
- `site.aclanthology.org 2023 tweetnlp multilingual sentiment Camacho Barbieri`

Además se abrieron las páginas originales de P01–P03, P05–P08, P11 y enlaces DOI del documento base. P04, P09 y P10 se localizaron en sus sitios editoriales. La bibliografía conserva destinos verificables; el nivel de lectura varía entre resumen, ficha y texto completo disponible. No se declaran tablas extraídas cuando solo se inspeccionó el resumen.

## Estrategia ampliada propuesta, aún no ejecutada

(`sentiment analysis` OR `análisis de sentimientos`) AND (`public services` OR `municipal` OR `waste collection` OR `limpieza pública`) AND (`Spanish` OR `Peru` OR `Juliaca`)

(`BETO` OR `Spanish BERT`) AND (`SVM` OR `TF-IDF`) AND (`sentiment` OR `sentimientos`)

Aplicar en bases bibliográficas y registrar campos, filtros, fechas, consultas exactas, exportaciones y decisiones. Priorizar 2021–2026; admitir fuentes fundacionales anteriores. El predominio reciente y la cobertura local todavía requieren ampliación.

## Criterios aplicados

Incluir publicaciones identificables relacionadas con clasificación, español/redes, residuos o métodos de evaluación. Admitir surveys y artículos fundacionales como categorías distintas. Excluir resultados comerciales sin fuente, referencias duplicadas y estudios de recomendación sin aporte al clasificador. No convertir estudios contextuales en evidencia experimental local.

## Correcciones y decisiones

- SEDICI: autores Rosenbrock, Trossero y Pascal, 2021; el resumen indica más de 50.000 reseñas. El PDF se cotejó después: corpus 52.309; tabla 1, F1 BETO 0,88 y SVM 0,79. El F1 de BETO queda confirmado, pero 10.462 no es el total del corpus.
- Sustainability 13788: autoría Jenkins y colaboradores; corregir la atribución a Thiagarajah.
- Weibo PMC11471487: la consulta inicial localizó el artículo; un segundo acceso fue bloqueado por comprobación de navegador. La identidad se corroboró después en PubMed: Sui y Zhang, Heliyon 2024, e38510. Se incorporó como P15 con extracción parcial; no usar cifras no comprobadas.
- Díaz Tunjar y Cayra Uscamayta: conservar como candidatos del documento base; comprobar tesis y metodología antes de incorporarlos como evidencia cuantitativa.
- Snowballing: se recuperaron fuentes originales a partir de referencias del material base. La búsqueda de citas posteriores y expansión desde bibliografías completas sigue pendiente.


## Ampliación ejecutada en esta revisión

Búsqueda web dirigida, seguida de lectura del original:

- `site.aclanthology.org RoBERTuito 2022`: P12, PDF, tabla 2.
- `site.aclanthology.org 2024 Spanish sentiment benchmark`: P13 y P14, PDFs, tablas 3/6 y 5 respectivamente.
- `"PMC11471487" sentiment`: P15, identidad y resumen en PubMed.
- `site.portal.core.edu.au/conf-ranks LREC 2023 A`: resultado LREC B, no A.
- `site.scimagojr.com "Sensors" "2023" "Q1"`: comprobación complementaria de CiteScore en informe editorial; no confundir sistemas.
- `site.scimagojr.com "Transactions of the Association for Computational Linguistics" "2023"`: ficha localizada, apertura bloqueada.

Selección: P12 por comparación con BETO en redes; P13 por tres clases en español y desacuerdo; P14 por restricciones de datos; P15 por residuos. TweetNLP se localizó como herramienta, sin agregarlo al núcleo para evitar duplicar el aporte de P08. No se registran conteos totales de buscador ni un flujo de selección exhaustiva. La ventana y las cadenas ampliadas anteriores siguen siendo un plan de búsqueda nativa, no consultas efectuadas en Scopus.
