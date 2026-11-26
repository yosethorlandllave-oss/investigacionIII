# Esquema del método

```mermaid
flowchart TD
 A[Acceso, fuentes y protocolo] --> B[Piloto y revisión de instrumentos]
 B --> C[Recolección y anonimización]
 C --> D[Dos anotaciones independientes y adjudicación]
 D --> E[Agrupar publicaciones y duplicados]
 E --> F[Entrenamiento 60 por ciento]
 E --> G[Validación 20 por ciento]
 E --> H[Prueba reservada 20 por ciento]
 F --> I[TF-IDF y SVM]
 F --> J[Ajuste de BETO]
 G --> K[Elegir configuración de cada modelo]
 I --> K
 J --> K
 K --> L[Congelar configuraciones]
 L --> M[Predicciones de ambos modelos]
 H --> M
 M --> N[Métricas y comparación pareada por grupos]
 N --> O[Errores, límites e informe]
```

OE1: A–E; OE2: F–L; OE3: M–N; OE4: O. Los porcentajes son aproximados y se ajustan respetando grupos. Las publicaciones piloto solo podrán alimentar entrenamiento. Las etiquetas de prueba no se emplearán para elegir configuración ni reglas. Privacidad, versiones y trazabilidad se aplican en todas las etapas.
