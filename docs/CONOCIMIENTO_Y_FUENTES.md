# Conocimiento fiable y uso de NotebookLM

## Objetivo

Transformar investigación en información trazable: cada recomendación debe tener una fuente que realmente respalde lo que dice, población aplicable, límites y fecha de revisión. Tener una cita no garantiza que la interpretación sea correcta.

NotebookLM permite trabajar con fuentes y consultar citas en el chat. Se propone usarlo para organizar la investigación, conservando siempre las referencias originales. [Ayuda oficial de Google](https://support.google.com/notebooklm/answer/16179559).

No se han leído tus cuadernos. Tampoco se ha verificado una integración programática adecuada a tu cuenta. El producto inicial no dependerá de una API de NotebookLM, de automatizar su interfaz ni de copiar respuestas en producción sin revisión.

## Flujo editorial

1. Reunir documentos originales: organismos públicos, guías profesionales, revisiones sistemáticas y estudios relevantes.
2. Organizarlos en cuadernos de proteína, alimentación, entrenamiento y etiquetado chileno.
3. Pedir resúmenes que separen resultados, población, limitaciones y discrepancias.
4. Abrir el documento original y comprobar cada afirmación que se quiera mostrar.
5. Completar una [ficha de fuente](../research/templates/FICHA_FUENTE.md).
6. Crear una [ficha de recomendación](../research/templates/FICHA_RECOMENDACION.md), indicando pasaje/página/sección que la sustenta.
7. Revisar y aprobar; sólo el contenido aprobado entra en `content/knowledge/`.
8. Publicar una versión y establecer próxima revisión. Retirar o reemplazar recomendaciones si cambia la evidencia.

Los documentos completos sólo se incorporan si se tiene permiso para ese uso. Guardar referencias y síntesis propias cuando no corresponda redistribuir el original.

## Qué contenido entra primero

- Cómo leer por 100 g, por 100 ml y por porción.
- Diferencia entre cantidad de producto y cantidad de proteína.
- Cómo pesar y registrar sin confundir crudo con cocido.
- Cómo interpretar la meta elegida y por qué tiene límites.
- Cómo registrar entrenamiento y comparar PB equivalentes.

Las sugerencias de alimentos pueden empezar con una regla matemática sobre favoritos confirmados: si faltan cierta cantidad de gramos, mostrar porciones que aporten una parte. Mostrar cantidad y aporte, respetar preferencias/alérgenos registrados y permitir ignorar. No afirmar que una opción compone por sí sola una dieta adecuada ni incentivar sobreconsumo.

## Evolución de las recomendaciones

**Etapa 1: fichas y reglas revisadas.** Funcionan sin conexión, con redacción controlada y referencias visibles. Los mensajes motivacionales no requieren IA.

**Etapa 2: recuperación de contenido aprobado.** Una consulta busca fichas aplicables por tema y contexto. No usa fuentes no revisadas como instrucciones ni acepta que un documento modifique reglas del sistema.

**Etapa 3: redacción asistida por IA.** Un servidor recibe contexto mínimo, recupera pasajes aprobados y genera una respuesta con referencias. El cálculo de cantidades sigue en funciones deterministas. Si falta evidencia o hay contradicción, la app lo explica en vez de fabricar citas.

La conversación no cambia metas, registros ni planes sin una acción explícita del usuario. Una respuesta educativa no se convierte automáticamente en recomendación clínica personalizada.

## Criterios de revisión

| Dimensión | Pregunta |
| --- | --- |
| Identidad | ¿Existe la fuente y coincide autor, fecha, título y enlace? |
| Respaldo | ¿El pasaje citado sostiene exactamente la afirmación? |
| Población | ¿A quién se estudió y a quién no se debe extrapolar? |
| Calidad | ¿Qué tipo de estudio/guía es y qué limitaciones presenta? |
| Vigencia | ¿Hay actualizaciones o fuentes que cambien la interpretación? |
| Coherencia | ¿Se conserva el rango, la unidad y la incertidumbre? |
| Presentación | ¿El usuario puede abrir la referencia y entender su alcance? |

Crear un conjunto de preguntas de evaluación antes de habilitar conversación: respuestas con respaldo, insuficiencia de evidencia, fuentes en desacuerdo y consultas fuera de alcance. Medir citas que sí respaldan la frase, no sólo respuestas que incluyen enlaces.

## Prompt reutilizable para tu investigación

> Usando únicamente las fuentes seleccionadas, resume la evidencia sobre [tema]. Para cada afirmación indica documento original, autor, año, población, resultado, límites y página o sección verificable. Distingue consenso, incertidumbre y resultados contradictorios. No inventes referencias ni conviertas resultados de una población en recomendaciones para otra. Enumera lo que no puede concluirse con estas fuentes.

Este prompt es apoyo de trabajo; las respuestas necesitan revisión contra los originales antes de publicarse.
