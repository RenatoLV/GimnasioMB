# Nutrición, cantidades y OCR

## Qué calculará la app

Se separan tres magnitudes: peso corporal en kg, carga de entrenamiento en kg y cantidad de alimento en g/ml/unidades. La interfaz nunca debe pedir un ambiguo «peso» sin contexto.

La meta de proteína es una estimación orientativa configurable. Cumplirla no garantiza alcanzar un peso corporal, y el faltante no equivale a una obligación de consumir suplementos.

## Meta diaria

```text
meta_proteina_g = peso_referencia_kg × factor_g_por_kg
consumido_g = suma de proteína de consumos confirmados del día
faltante_g = máximo(0, meta_proteina_g − consumido_g)
```

Como referencia para estudiar una regla dirigida a adultos sanos que entrenan, el posicionamiento ISSN de 2017 describe un rango de 1,4–2,0 g/kg/día para la mayoría de personas que hacen ejercicio. No se aplica automáticamente a toda persona ni se presenta como la última revisión disponible. [Artículo y población de referencia](https://pubmed.ncbi.nlm.nih.gov/28642676/).

Antes de publicar una meta guiada: revisar evidencia actualizada con un profesional, documentar selección del factor y condiciones de aplicación. En menores, embarazo/lactancia o condiciones que requieran indicación clínica, no activar esa regla general; permitir registro y una meta definida con su profesional sin intentar diagnosticar.

Primera entrega: meta manual o configurada con explicación explícita. No inferirla sólo desde «quiero subir/bajar de peso». El peso de referencia será una medición elegida, normalmente la actual; no sustituirlo silenciosamente por el peso deseado.

Ejemplo ficticio de la fórmula, no recomendación personal: 70 kg × factor elegido de 1,6 = 112 g/día. Si se registran 82 g, el faltante mostrado es 30 g. Si se supera la meta, el faltante es cero y el total real sigue visible.

Cada meta guarda fecha de vigencia, método, fuente/versión, factor y peso usado. Un cambio de peso no reescribe las metas históricas ni la meta de hoy sin confirmación.

## Conversión de alimentos

```text
nutriente_consumido = nutriente_por_100 × cantidad_consumida / 100
nutriente_consumido = nutriente_por_porcion × numero_de_porciones
```

Elegir una base válida para el alimento. Ejemplo ficticio: 8 g de proteína por 100 g y 150 g consumidos producen 12 g de proteína. Una porción de 30 g con 24 g de proteína y 1,5 porciones consumidas produce 36 g de proteína en 45 g de producto. **Gramos de polvo y gramos de proteína son datos distintos.**

No convertir ml a g sin densidad conocida. Para «unidad», «cucharada» o «scoop», exigir equivalencia específica del producto o conservar sólo una porción con nutrientes declarados. Los valores desconocidos se guardan como desconocidos, no como cero.

Si sólo se sabe proteína, los demás totales se muestran incompletos. Un «0» impreso puede reflejar redondeo: conservar la precisión/origen de etiqueta. Para valores como «<0,5», conservar el límite; no inventar una lectura exacta. Cálculos con precisión interna suficiente y redondeo sólo al mostrar.

## Cantidad medida y estimada

| Método | Qué se guarda | Cómo se muestra |
| --- | --- | --- |
| Balanza | Cantidad, unidad y origen manual | Medido por el usuario |
| Porción del envase | Número de porciones y equivalencia declarada | Según etiqueta |
| Medida casera | Equivalencia específica y referencia | Estimado |
| Cantidad aproximada | Valor central y rango opcional | Aproximado, editable |
| Foto del plato, futuro | Método, rango y confirmación | Estimación visual, nunca peso medido |

Una foto de la etiqueta identifica información nutricional; no mide cuánto comiste. La primera versión siempre pide cantidad o porciones. Para una receta futura, sumar nutrientes de ingredientes y dividir por peso final preparado o porciones conocidas. Mantener separado crudo/cocido y registrar rendimiento: no usar indistintamente los gramos de ambos estados.

## Etiquetas chilenas

El artículo 115 del Reglamento Sanitario de los Alimentos contempla información por 100 g/100 ml y por porción de consumo habitual. El lector debe reconocer ambas bases y evitar mezclarlas. [BCN, artículo 115, texto consultado de 2024](https://www.bcn.cl/leychile/navegar?idNorma=71271&idParte=8716443&idVersion=2024-01-27). Revisar el texto consolidado vigente antes del lanzamiento; esta referencia no certifica cobertura de cambios posteriores.

Campos del borrador: nombre, marca opcional, cantidad de porción, unidad, porciones por envase, base de columna, energía, proteína, carbohidratos, grasas y sodio. Azúcares, grasas saturadas y fibra se guardan cuando estén disponibles. Los sellos frontales no sustituyen la tabla ni permiten completar nutrientes ausentes.

## Flujo de OCR

1. Pedir permiso y mostrar guía de encuadre para la tabla completa.
2. Capturar foto, permitir recorte y repetición por desenfoque o reflejos.
3. Extraer texto y posiciones en el dispositivo cuando sea viable.
4. Reconstruir encabezados, filas, columnas, números y unidades.
5. Normalizar «Proteínas», «Proteina», coma/punto decimal y espacios conservando el texto original.
6. Validar campos y señalar incoherencias; no autocorregir cifras dudosas sin revisión.
7. Mostrar foto junto al formulario y pedir confirmación de proteína, base y porción.
8. Guardar una versión del alimento. Luego, por separado, registrar cantidad consumida.

Estados: captura → procesando → borrador → requiere revisión → confirmado; también cancelado/error. Sólo los consumos confirmados participan en el total.

La confianza por campo será una medida interna de validación, no una probabilidad inventada. Si el motor no informa confianza, usar «lectura pendiente de revisión», coincidencia de encabezado y controles de consistencia. No presentar porcentajes sin calibración.

## Validaciones

- Proteína, cantidad, unidad y base deben estar confirmadas para calcular el consumo.
- No aceptar negativos ni dividir por porción cero; advertir rangos imposibles.
- Proteína por 100 g no puede superar 100 g. No aplicar el mismo límite sin contexto a 100 ml.
- Distinguir g y mg, kcal y kJ, alimento seco y preparado, porción y envase.
- Contrastar las dos columnas cuando la equivalencia esté disponible, admitiendo redondeos documentados.
- Una incoherencia deja el dato en revisión, no lo reemplaza por un cálculo de IA.
- Si la foto es ilegible o se deniega cámara, mantener alta manual disponible.
- Un código de barras identifica un producto, pero necesita un catálogo y no prueba que su etiqueta esté actualizada.

## Casos de aceptación futuros

| Caso | Resultado esperado |
| --- | --- |
| 8 g/100 g, consumo 150 g | 12 g de proteína |
| 3,2 g/100 ml, consumo 250 ml | 8 g de proteína |
| 24 g/porción, 1,5 porciones | 36 g de proteína |
| Meta 112 g, consumido 120 g | Faltante 0; total 120 |
| Dos columnas, porción 30 g | No confundir cifra por 100 g con cifra por porción |
| Etiqueta indica «<0,5» | Mantener límite e incertidumbre |
| Sodio 200 mg | No guardar 200 g |
| Editar alimento ya consumido | El historial conserva la versión anterior |
| No se conoce energía | Mostrar total de energía incompleto |
| Borrar consumo confirmado | Recalcular día y registrar cambio |

Son especificaciones de pruebas para la implementación; no son funcionalidades ni pruebas ya ejecutadas.
