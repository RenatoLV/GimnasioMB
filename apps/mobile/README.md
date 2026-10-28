# Aplicación móvil

Carpetas preparadas para React Native + Expo + TypeScript. **Aún no se ha inicializado el framework y no hay comandos de ejecución disponibles.**

## Organización prevista

- `src/app/`: rutas y navegación.
- `src/features/profile/`: perfil, peso y metas.
- `src/features/nutrition/`: alimentos, porciones y consumos.
- `src/features/scanner/`: captura y revisión de etiquetas.
- `src/features/workouts/`: sesiones, ejercicios y series.
- `src/features/records/`: PB y comparaciones.
- `src/features/history/`: calendario y tendencias.
- `src/features/companion/`: configuración y presentación del motivador.
- `src/features/knowledge/`: fichas educativas y fuentes.
- `src/components/` y `src/theme/`: interfaz compartida.
- `src/domain/`: cálculos y reglas independientes de la UI.
- `src/data/`: persistencia y consultas.
- `src/services/`: integración con dispositivo y servicios externos.
- `assets/`: recursos originales o con licencia documentada.

Al inicializar Expo, usar un proyecto temporal si el generador exige una carpeta vacía y trasladar sus archivos sin sobrescribir esta planificación. Elegir versiones estables compatibles en ese momento. Revisar el [plan de arquitectura](../../docs/ARQUITECTURA.md) antes de añadir dependencias.
