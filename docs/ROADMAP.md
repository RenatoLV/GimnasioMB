# Hoja de ruta y backlog inicial

Estimaciones orientativas para una persona con experiencia en el stack y dedicación sostenida. No son fechas comprometidas. Aprendizaje, arte, revisión de fuentes y problemas de módulos nativos pueden ampliar cada etapa.

## Entregas

| Etapa | Resultado | Esfuerzo orientativo | Dependencia |
| --- | --- | --- | --- |
| 0. Validación | Flujos, primeras fuentes y prueba técnica de OCR en teléfono | 3–5 días | Teléfono y etiquetas de prueba |
| 1. Núcleo local | Perfil, meta, alimentos manuales, consumo e historial diario | 1–2 semanas | Modelo y unidades definidos |
| 2. OCR | Escaneo, revisión, alimento guardado y consumo | 1–2 semanas | Prueba de módulo OCR y núcleo local |
| 3. Entrenamiento | Sesiones, series, duración, PB y peso histórico | 1–2 semanas | Persistencia estable |
| 4. Experiencia | Personaje básico, fichas revisadas, copias y accesibilidad | 1–2 semanas | Contenido y arte originales disponibles |
| 5. Beta | Recuperación, pruebas en dispositivos y ajustes | 1–2 semanas | Etapas previas integradas |
| 6. Ampliaciones | Recetas, más personajes, nube y recomendaciones asistidas | Reestimar | Evidencia de uso y prioridades de beta |

Las etapas 1–5 componen el MVP. La prueba temprana de OCR identifica riesgos, pero el primer flujo completo de producto usa registro manual.

## Backlog con aceptación

| ID | Prioridad | Historia | Terminado cuando |
| --- | --- | --- | --- |
| BASE-01 | P0 | Iniciar el proyecto móvil | Arranca en Android y tiene navegación básica; versiones fijadas |
| DATA-01 | P0 | Persistir registros locales | Cerrar y abrir conserva datos; migración inicial documentada |
| PRO-01 | P0 | Configurar peso y meta | Unidades claras; meta manual y fundamento del método visibles |
| FOOD-01 | P0 | Crear un alimento | Admite base por 100 g/ml o porción; campos desconocidos no valen cero |
| FOOD-02 | P0 | Registrar consumo | Cantidad confirmada produce total correcto, editable y sin duplicación |
| DAY-01 | P0 | Consultar progreso diario | Total y faltante correctos en fecha local; días pasados accesibles |
| OCR-01 | P0 | Evaluar módulo nativo | Lee texto/posiciones en teléfono y documenta compatibilidad y modo offline |
| OCR-02 | P0 | Escanear una etiqueta chilena | Distingue columnas/unidades y exige revisión antes de guardar |
| HIST-01 | P0 | Conservar historia | Cambiar etiqueta/meta no modifica registros anteriores sin acción explícita |
| TRAIN-01 | P1 | Registrar sesión y series | Soporta pausa, reanudación, finalización y entrada manual |
| PB-01 | P1 | Identificar récord | Compara variantes equivalentes; editar/borrar recalcula resultados |
| PET-01 | P1 | Tener motivador básico | Nombre/tono configurables; mensajes usan datos reales y se puede ocultar |
| KNOW-01 | P1 | Consultar información respaldada | Cada ficha publicada tiene fuente, pasaje, límites y revisión |
| DATA-02 | P1 | Exportar/restaurar/borrar | Copia verificable y restauración sin duplicados; borrado local completo |
| QA-01 | P1 | Preparar beta | Flujos principales y casos de recuperación aprobados en dispositivos |
| SYNC-01 | P2 | Usar varios dispositivos | Políticas de acceso, reintentos y conflictos validados con dos usuarios |
| AI-01 | P2 | Consultar recomendaciones asistidas | Respuestas trazables, evaluación de citas y abstención sin evidencia |

P0: necesario para el primer recorrido útil. P1: completa el MVP. P2: posterior. La aceptación de una fila todavía está pendiente: esta entrega sólo crea planificación.

## Pruebas necesarias al implementar

- Cálculos: gramos/ml/porciones, decimales, valores ausentes y redondeos.
- Historial: edición, borrado, meta versionada, medianoche y horario de verano.
- Entrenamiento: pausas, cierre inesperado, empates de PB y correcciones de series.
- OCR: un conjunto inicial de 30–50 etiquetas variadas con transcripción humana de referencia. Separar ejemplos de ajuste y evaluación; medir exactitud por campo y tasa de corrección humana. Es una muestra piloto, no una promesa de cobertura nacional.
- Persistencia: actualización de esquema, falta de espacio, copia y restauración.
- Experiencia: primer uso, cámara denegada, campos con lector de pantalla y movimiento reducido.
- Nube, cuando exista: pruebas de aislamiento entre usuarios y borrado/sincronización.
- Conocimiento: revisión humana del respaldo de cada ficha; evaluación de respuestas antes de activar IA.

## Criterio de salida de beta

Una persona puede registrar un día completo de alimentación y entrenamiento, consultar su meta y PB, volver después de cerrar la app y recuperar los datos. Puede identificar y corregir una lectura OCR dudosa, distinguir estimaciones, consultar fuentes y exportar o borrar su historial.

## Riesgos y cómo resolverlos

| Riesgo | Acción |
| --- | --- |
| Alcance excesivo | Entregar el ciclo de proteína antes de editor de personajes y chatbot |
| OCR confunde columnas | Revisión visible y conjunto de etiquetas reales de prueba |
| Dependencia nativa incompatible | Prueba en etapa 0; adaptador intercambiable y alta manual |
| Recomendación fuera de contexto | Fichas con población/límites y revisión profesional antes de publicación |
| Historial cambia al editar catálogo | Versiones de alimentos, metas y copias de cálculos |
| Animación consume batería o distrae | Animaciones breves, pausa fuera de pantalla y desactivación |
| Pérdida del teléfono | Copia local exportable primero; nube opcional después |
| Costos de IA o nube | Medir uso, establecer límites y conservar funciones locales |

## Próxima acción concreta

Crear el proyecto Expo dentro de `apps/mobile/` respetando las carpetas existentes. Implementar únicamente Hoy, formulario de alimento, registro de consumo y almacenamiento local. Comprobar el ejemplo ficticio de 8 g/100 g × 150 g = 12 g, cerrar/reabrir y verificar el historial. En paralelo al diseño de esos flujos, validar el módulo OCR en el dispositivo de destino; no hace falta construir una cuenta ni un servidor para esta entrega.
