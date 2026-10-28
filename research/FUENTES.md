# Registro inicial de fuentes

Consulta web realizada el **28 de octubre de 2026**. Este registro documenta el fundamento del plan; no equivale a revisión clínica ni a aprobación de contenido para usuarios finales. No incluye todavía tus fuentes privadas de NotebookLM.

| ID | Fuente original | Uso en este plan | Estado / límite |
| --- | --- | --- | --- |
| NUT-001 | [ISSN: Protein and exercise, 2017](https://pubmed.ncbi.nlm.nih.gov/28642676/) | Referencia para estudiar una regla de proteína en población que entrena | Revisar actualización y aplicabilidad antes de publicar |
| CL-001 | [BCN: Decreto 977, artículo 115, versión consultada 2024-01-27](https://www.bcn.cl/leychile/navegar?idNorma=71271&idParte=8716443&idVersion=2024-01-27) | Estructura de etiquetado por base y porción | Referencia histórica consultada; verificar consolidado vigente para lanzamiento |
| CL-002 | [MINSAL: Reglamento Sanitario, documento actualizado a mayo de 2024](https://www.minsal.cl/wp-content/uploads/2015/10/DECRETO_977_96_actualizado_-mayo-2024.pdf) | Documento de apoyo para estudiar formatos | No asumir que contiene modificaciones posteriores |
| TECH-001 | [Expo Camera](https://docs.expo.dev/versions/latest/sdk/camera/) | Captura de imágenes | Confirmar versión compatible al instalar |
| TECH-002 | [Expo SQLite](https://docs.expo.dev/versions/latest/sdk/sqlite/) | Persistencia local | Probar migraciones y configuración seleccionada |
| TECH-003 | [Expo development builds](https://docs.expo.dev/develop/development-builds/introduction/) | Incorporación de módulos nativos | Verificar OCR en dispositivo |
| TECH-004 | [EAS Build](https://docs.expo.dev/build/introduction/) | Compilación remota | Revisar condiciones y costos al usar |
| TECH-005 | [Google ML Kit: Text Recognition v2](https://developers.google.com/ml-kit/vision/text-recognition/v2) | Candidato para extraer texto de etiquetas | No resuelve por sí solo la interpretación nutricional |
| TECH-006 | [Supabase: Row Level Security](https://supabase.com/docs/guides/database/postgres/row-level-security) | Aislamiento futuro de datos por usuario | Sólo si se implementa nube |
| TECH-007 | [Flutter: integración multiplataforma](https://docs.flutter.dev/platform-integration) | Alternativa de framework | Decisión depende de experiencia y prueba técnica |
| KNOW-001 | [Google: chat y fuentes de NotebookLM](https://support.google.com/notebooklm/answer/16179559) | Flujo de investigación con citas | La ayuda puede redirigir por cambios de nombre; no demuestra integración con esta app |
| ART-001 | [Kasane Teto: guías oficiales](https://kasaneteto.jp/guideline/) | Identificar condiciones para personaje y voz | Evaluar uso específico si se decide incorporarlos |

## Material todavía necesario

- Fuentes de tus cuadernos: título, autor, fecha, enlace/DOI y pasaje relevante.
- Revisión actualizada para metas de proteína y población de destino.
- Referencias de técnica de ejercicios y criterios para futuras estimaciones de 1RM.
- Etiquetas chilenas de prueba con transcripción y permiso de uso cuando corresponda.
- Licencia y procedencia de cualquier arte, audio o catálogo de alimentos incorporado.

## Organización

`research/notebooklm/` recibe notas de investigación; `research/templates/` contiene fichas reutilizables. `research/private/` está excluida de Git para trabajo local sensible: esa exclusión no cifra archivos ni sustituye una política de protección de datos.

El contenido aprobado se publica en `content/knowledge/` y sus referencias en `content/sources/`. No mover automáticamente un resumen generado a esas carpetas como si ya estuviera revisado.
