# Plan de la aplicación

## 1. Propuesta

Ayudar a responder tres preguntas diarias: **qué consumí, cómo entrené y qué me falta para mi objetivo**. Un compañero personalizable acompaña el proceso con mensajes útiles y respetuosos.

El diferencial será la combinación de etiquetas chilenas, registro rápido reutilizable, historial consistente y explicaciones con fuentes consultables. La mascota aporta identidad; la precisión del registro sostiene la utilidad.

## 2. Supuestos iniciales editables

| Decisión | Propuesta inicial |
| --- | --- |
| Público | Público general de distintas edades, con información adaptada a etapa de vida, actividad y contexto; no centrado en adultos mayores |
| Plataforma | Android primero; preparar iOS desde la arquitectura |
| Idioma y unidades | Español de Chile, kg, g, ml, kcal y coma decimal en pantalla |
| Framework | React Native + Expo + TypeScript |
| Acceso | Uso local sin cuenta para la primera versión |
| PB | Personal Best: récord personal; también se puede mostrar como PR |
| Peso corporal | Mediciones fechadas y tendencia; separado del peso levantado |
| Cantidad de alimento | Medida o estimada, siempre identificada |
| Meta de proteína | Editable, con método, peso de referencia y fuente registrados |
| Personaje | Original, reemplazable y opcional |
| NotebookLM | Herramienta de investigación; integración automática no asumida |

No se conocen todavía tu experiencia de programación, teléfono de prueba, presupuesto ni biblioteca de fuentes. Estas propuestas permiten empezar y pueden cambiar antes de implementar.

La app contempla niños, adolescentes, adultos y personas mayores. El perfil debe distinguir etapa de vida y adaptar metas, mensajes y ejercicios según evidencia específica. Para infancia temprana se deberá definir una experiencia gestionada por un adulto responsable. Una regla estudiada en adultos que entrenan no se extiende automáticamente a todas las edades. La cobertura de recomendaciones se habilita por población cuando existan fuentes revisadas.

## 3. Alcance por versión

| Área | Primera versión útil: MVP | Versión siguiente | Más adelante |
| --- | --- | --- | --- |
| Perfil | Peso, objetivo, unidades, meta diaria | Medidas corporales opcionales | Integraciones con dispositivos |
| Alimentación | Alimentos manuales, favoritos, cantidad, historial | Recetas, comidas reutilizables, código de barras | Catálogo compartido moderado |
| Proteína | Total diario, faltante y meta versionada | Sugerencias desde alimentos guardados | Personalización avanzada validada |
| OCR | Foto de etiqueta, revisión y guardado | Mejoras de formatos y detección de duplicados | Ayuda visual para porciones con incertidumbre |
| Entrenamiento | Ejercicios, series, carga, repeticiones, duración | Rutinas, RPE/RIR, descansos, cardio detallado | Integración con relojes |
| PB | Mayor carga y repeticiones a igual carga | Volumen por sesión y 1RM estimado | Comparativas avanzadas |
| Historial | Día, semana, peso, comidas, entrenamientos y PB | Tendencias mensuales y exportación ampliada | Informes compartidos voluntariamente |
| Compañero | Un personaje original, nombre y mensajes por eventos | Chibi/gato/perro/humano, accesorios, colores | Editor avanzado y voz con permisos |
| Fuentes | Fichas educativas curadas y referencias | Búsqueda y recomendaciones contextuales | Conversación con recuperación de fuentes |
| Datos | SQLite, exportación/restauración local, borrado | Cuenta y copia en nube | Sincronización entre dispositivos |

El MVP se construye por entregas: primero registro manual y persistencia; luego OCR; después entrenamiento y personaje. No es necesario construir todas sus pantallas simultáneamente.

## 4. Lo que queda fuera del lanzamiento

- Diagnóstico, prescripción clínica o dietas terapéuticas automatizadas.
- Calcular el peso exacto de una comida a partir de una sola foto.
- Prometer que una cantidad de proteína producirá cierto peso corporal.
- Restar automáticamente calorías de ejercicio a lo consumido.
- Red social, mercado de personajes, pagos, publicidad y voz clonada.
- Un chatbot abierto antes de tener un catálogo de fuentes revisado.

## 5. Flujos principales

### Primer uso

Elegir unidades → registrar peso corporal con fecha → indicar objetivo → configurar meta de proteína → elegir compañero → llegar a Hoy. El cálculo guiado explica sus supuestos; también se admite una meta indicada por un profesional. Los campos sin uso en esta etapa no se solicitan.

### Registrar comida

Buscar favorito, crear alimento o escanear etiqueta → revisar nutrientes y base de medida → indicar cantidad consumida → confirmar → actualizar el día. Guardar un alimento en la biblioteca y registrar que se consumió son acciones diferentes.

### Registrar entrenamiento

Iniciar sesión → elegir ejercicio → registrar series → pausar o continuar → finalizar → mostrar duración y nuevos PB. También se puede registrar una sesión pasada manualmente.

### Consultar una recomendación

Ver sugerencia contextual → abrir explicación → consultar población, límites, fecha de revisión y fuente original. La app muestra cuándo no dispone de evidencia suficiente.

## 6. Navegación propuesta

| Pantalla | Contenido principal | Acción destacada |
| --- | --- | --- |
| Hoy | Proteína registrada/meta, acceso al compañero y actividad del día | Registrar comida |
| Alimentación | Biblioteca, favoritos, comidas y escáner | Escanear etiqueta |
| Entrenamiento | Sesión actual, ejercicios y PB | Iniciar entrenamiento |
| Historial | Calendario, peso y resúmenes comparables | Consultar día |
| Perfil | Metas, personaje, fuentes, privacidad y copias | Editar meta |

El personaje se abre desde Hoy o Perfil; no necesita una sexta pestaña. Una recomendación tiene su propia vista con referencias. Formularios, confirmación OCR y detalle de ejercicio se abren dentro de su flujo.

## 7. Medidas de éxito propuestas

Medir primero en pruebas voluntarias con datos de ejemplo:

- Registrar un alimento favorito en menos de 20 segundos: objetivo de diseño, todavía sin medir.
- Completar el ciclo etiqueta → alimento → consumo sin confundir columnas ni unidades.
- Recuperar todos los registros tras cerrar la app o interrumpir una sesión.
- Entender si una cantidad fue pesada o estimada y de dónde salió la meta.
- Encontrar la fuente de una recomendación en dos acciones o menos.
- Elegir entre continuar con el compañero, cambiarlo o desactivarlo.

No usar bajar de peso, comer menos o superar la meta de proteína como medidas universales de éxito.

## 8. Decisiones para antes de implementar

Elegir nombre, teléfono de prueba, Android/iOS prioritario, estilo del primer personaje y tiempo disponible. Confirmar si hay experiencia previa con React/TypeScript o Flutter/Dart. Reunir primeras etiquetas y fuentes de NotebookLM. Para una beta pública: definir presupuesto, soporte, revisión nutricional y tratamiento de datos aplicable.

Los costos previstos son desarrollo, arte, revisión profesional y dispositivos; posteriormente tiendas, compilación remota, almacenamiento y consultas de IA. No se fija una tarifa sin cotizar el servicio y volumen al momento de contratar.
