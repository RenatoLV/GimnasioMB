# Personajes y experiencia móvil

## Identidad

La app puede tener una estética moderna, cálida y lúdica: tarjetas claras, números legibles y un compañero chibi en momentos concretos. La nutrición y el entrenamiento conservan prioridad visual.

Propuesta inicial: un personaje original con espíritu de cantante/anime chibi, reemplazable más adelante por gato, perro o compañero humano. El tipo de personaje cambia aspecto y tono, no las reglas nutricionales.

Kasane Teto sirve como referencia de lo que te gusta. Para incluir su identidad, ilustraciones o voz concretas se debe revisar el uso previsto en sus condiciones oficiales; hay apartados diferentes para personaje y material sonoro. No asumir que una autorización para un recurso cubre los demás. [Guías oficiales](https://kasaneteto.jp/guideline/). La primera propuesta de producto usa arte original.

## Personalización por etapa

| Etapa | Opciones |
| --- | --- |
| MVP | Un personaje, nombre, tono amable/directo, mostrar/ocultar, reducir movimiento |
| Segunda versión | Chibi, gato, perro, humano; colores, pelo/pelaje, ropa y accesorios compatibles |
| Futuro | Paquetes de arte, editor de capas, avatar inspirado en alguien, voz autorizada |

Un avatar de pareja puede tener nombre y apariencia elegidos por el usuario. Si usa fotos o voz de una persona real, exigir permiso para ese uso y ofrecer eliminación. No hace falta una foto para crear un personaje humano personalizado.

Cada personaje define estados comunes: reposo, saludo, registro completado, entrenamiento, celebración y descanso. Los accesorios declaran qué cuerpos y animaciones admiten; no asumir que la ropa de un humano encajará en un perro.

## Motivación basada en eventos

| Evento | Mensaje de ejemplo |
| --- | --- |
| Comida guardada | «Registro listo. Hoy llevas 82 g según tus alimentos guardados.» |
| Faltante respecto de meta | «Quedan 30 g para la meta que elegiste. Puedes revisar tus opciones guardadas.» |
| Entrenamiento terminado | «Sesión guardada: 45 minutos activos. ¿Quieres revisar tus series?» |
| PB confirmado | «Nuevo récord en este ejercicio: 8 repeticiones con 30 kg.» |
| Regreso después de una pausa | «Qué bueno verte. Puedes retomar con un registro sencillo.» |

Las cantidades siempre llegan del motor de cálculo. Las plantillas no inventan cifras. El compañero no castiga por faltar, no condiciona afecto a cumplir metas y no felicita automáticamente por comer menos o entrenar con dolor. Descanso y recuperación son experiencias válidas.

No usar rachas que se pierdan para presionar. Si existen logros, premiar constancia flexible y aprendizaje. Notificaciones optativas, horario silencioso y control de frecuencia; nunca mensajes culpabilizantes.

## Pantalla Hoy: boceto de contenido

```text
Hoy · miércoles 28                        Perfil

Proteína registrada                82 / 112 g
Faltan 30 g para tu meta elegida
[ Registrar alimento ] [ Escanear ]

Compañero pequeño + mensaje breve
[ Ver opciones guardadas ]

Entrenamiento de hoy
45 min activos · 6 ejercicios       Ver sesión

Último peso registrado             70 kg · fecha
Información útil                   Cómo leer una porción →

Hoy | Alimentación | Entrenamiento | Historial | Perfil
```

Cifras ficticias para diseñar. El personaje no oculta el formulario ni interrumpe cada registro. Las celebraciones se pueden saltar.

## Lenguaje visual y accesibilidad

Fondo neutro, un acento principal y un color secundario para acciones; no convertir comida en «buena/mala» mediante rojo/verde. Mostrar progreso con texto además de color. Tipografía escalable, contraste comprobado y controles amplios para uso con una mano.

Modo claro/oscuro, etiquetas para lectores de pantalla, opción de movimiento reducido y campos numéricos con unidad visible. Los errores indican cómo corregirlos y mantienen los datos ya ingresados. La pantalla OCR muestra los valores sospechosos y permite alta manual.

Separar assets, configuración de apariencia y catálogo de mensajes. Ninguna imagen ni voz viene incluida en esta estructura inicial; `assets/characters/` reserva su ubicación.
