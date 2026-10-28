# GymnasioMobil

Proyecto **GimnasioMB**: aplicación móvil para apoyar el ejercicio, el consumo de proteína, las buenas prácticas y la formación de una rutina con motivación personalizable.

Estado: **planificación y estructura de carpetas; todavía no hay una app ejecutable**.

Fecha: 28 de octubre de 2026. Nombre de trabajo: GymnasioMobil; identidad comercial por definir.

Una app móvil para registrar alimentos, calcular el progreso hacia una meta de proteína, llevar entrenamientos y récords personales, y recibir motivación de un personaje configurable. El punto de partida es escanear etiquetas nutricionales chilenas y reutilizar los alimentos guardados.

## Empieza aquí

- [Templates visuales UI/UX](design/templates/ui-ux/README.md): seis pantallas de referencia, imágenes y prompts para iterar el diseño.

- [Alcance y decisiones del proyecto](docs/ALCANCE.md): público, entregables y límites por etapa.

- [Plan de la aplicación](docs/PLAN_APLICACION.md): visión, alcance, prioridades y pantallas.
- [Arquitectura y framework](docs/ARQUITECTURA.md): propuesta React Native + Expo + TypeScript y alternativas.
- [Nutrición y OCR chileno](docs/NUTRICION_Y_OCR.md): cálculos, cantidades, validaciones y límites.
- [Modelo de datos](docs/MODELO_DATOS.md): historial, alimentos, entrenamientos y fuentes.
- [Conocimiento y NotebookLM](docs/CONOCIMIENTO_Y_FUENTES.md): cómo llevar la investigación a recomendaciones verificables.
- [Personajes y experiencia](docs/PERSONAJES_Y_UX.md): chibi, gato, perro y compañero humano personalizable.
- [Hoja de ruta](docs/ROADMAP.md): entregas y criterios para darlas por terminadas.
- [Registro de fuentes](research/FUENTES.md): referencias consultadas y decisiones pendientes de revisión.
- [Búsquedas para NotebookLM](research/BUSQUEDAS_NOTEBOOKLM.md): cinco líneas de investigación con consultas listas para usar.

## Estructura inicial

```text
apps/mobile/                  Futuro proyecto móvil
  src/app/                    Navegación y pantallas
  src/features/               Funciones organizadas por dominio
  src/components/             Componentes visuales compartidos
  src/theme/                  Colores, tipografía, espaciado
  src/domain/                 Cálculos y reglas independientes de la interfaz
  src/data/                   SQLite, repositorios y futuras migraciones
  src/services/               Cámara, OCR y futuros servicios remotos
  assets/                     Personajes, iconos e imágenes
backend/                      Reserva para sincronización y recomendaciones remotas
content/                      Fuentes revisadas, recomendaciones y personajes
design/                       Flujos, pantallas y referencias visuales
docs/                         Planificación y decisiones
research/                     Investigación, plantillas y material privado excluido
tests/                        Casos futuros de cálculos, OCR, historial y sincronización
```

Los archivos `.gitkeep` conservan carpetas vacías al usar Git. No se instalaron dependencias, no se creó una cuenta de nube y no hay conexión con tus cuadernos de NotebookLM.

## Primera entrega propuesta

Registrar peso corporal y una meta de proteína; guardar un alimento manualmente; registrar gramos o porciones consumidas; ver el total diario y recuperar el historial al cerrar y abrir la app. Después, añadir cámara y OCR sin cambiar las reglas de cálculo.

La estructura permite desarrollar por partes. Las carpetas reservadas para etapas posteriores no implican que haya que implementar todo desde el inicio.
