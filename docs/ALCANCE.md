# Alcance de GymnasioMobil

Repositorio: [RenatoLV/GimnasioMB](https://github.com/RenatoLV/GimnasioMB).

## Propósito y público

Aplicación móvil para registrar alimentación y entrenamiento, consultar el progreso hacia una meta de proteína y recibir motivación de un compañero personalizable. El público es general y de distintas edades; no está centrado en adultos mayores.

La interfaz y la evidencia deben adaptarse a la etapa de vida. Incluir a todas las edades en el concepto no implica usar el mismo cálculo nutricional para todas. La cobertura de recomendaciones se habilitará por población según las fuentes revisadas. En edades tempranas, definir un uso gestionado por un adulto responsable.

## Alcance funcional

| Módulo | Qué abarca | Entrega |
| --- | --- | --- |
| Perfil y metas | Peso corporal fechado, etapa de vida, unidades y objetivo de proteína con método explícito | MVP |
| Alimentación | Biblioteca, favoritos, cantidades medidas/estimadas, proteína y otros nutrientes disponibles | MVP |
| OCR chileno | Captura de tabla nutricional, lectura de columnas, revisión y guardado | MVP, después del registro manual |
| Entrenamientos | Ejercicios, series, repeticiones, carga y duración con pausas | MVP |
| PB | Récords comparables por ejercicio y modalidad; actualización tras corregir registros | MVP básico |
| Historial | Comidas, peso corporal, entrenamientos, metas vigentes y progreso | MVP |
| Motivador | Personaje original básico, nombre, tono y opción de ocultarlo | MVP |
| Conocimiento | Fichas revisadas, límites y fuente original consultable | MVP |
| Datos | Guardado local, exportación, restauración y borrado | MVP |
| Personalización ampliada | Chibi, gato, perro o avatar humano, colores y accesorios | Posterior |
| Funciones ampliadas | Recetas, rutinas, gráficos avanzados y catálogo de productos | Posterior |
| Nube e IA | Cuenta opcional, sincronización y respuestas con recuperación de fuentes | Posterior, con evaluación propia |

## Recorrido que valida el concepto

Crear perfil y meta → guardar alimento → indicar cantidad consumida → consultar total y faltante diario → registrar entrenamiento → consultar historial y PB → recibir un mensaje del compañero. El OCR acelera el alta del alimento, manteniendo la confirmación humana.

## Comentarios sobre el alcance

- **Prioridad:** cerrar el recorrido de registro y cálculo antes de ampliar el editor de personajes. La utilidad diaria permite evaluar qué personalización vale la pena construir.
- **Precisión:** leer nutrientes de una etiqueta y estimar el peso de un plato son problemas diferentes. La primera entrega solicita cantidad o porciones y distingue lo medido de lo estimado.
- **Proteína:** la meta y el faltante son cálculos explicables; no garantizan un peso corporal ni implican recomendar suplementos.
- **Fuentes:** NotebookLM apoya la investigación. El contenido publicado conserva referencias originales, población, límites y fecha de revisión.
- **Historial:** modificar una etiqueta o una meta no cambia silenciosamente lo registrado en días anteriores.
- **Personajes:** comenzar con arte original. Incorporar una identidad específica como Kasane Teto exige revisar las condiciones de los recursos concretos que se quieran usar.
- **Framework:** React Native + Expo + TypeScript es la propuesta inicial; validar cámara y OCR en teléfono antes de fijar dependencias.
- **Publicación:** las estimaciones de la hoja de ruta son orientativas. Antes de una beta, revisar experiencia por edad, fuentes, accesibilidad y recuperación de datos.

## Estado de esta entrega

Concepto, Markdown de planificación y estructura de carpetas. No hay aplicación ejecutable, modelos de IA entrenados, conexión con NotebookLM ni infraestructura remota desplegada.

Las especificaciones detalladas están en [Plan](PLAN_APLICACION.md), [Arquitectura](ARQUITECTURA.md), [Nutrición y OCR](NUTRICION_Y_OCR.md), [Modelo de datos](MODELO_DATOS.md) y [Roadmap](ROADMAP.md).
