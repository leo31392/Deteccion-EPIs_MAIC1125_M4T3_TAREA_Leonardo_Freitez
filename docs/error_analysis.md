# Análisis de Errores - Tarea M4T3

## Falsos Positivos (FP) identificados
1. **Confusión de textura/color:** El modelo detectó un elemento de la estructura pintado de amarillo como un `helmet`. *Por qué:* El color y el reflejo del sol confundieron los filtros convolucionales del modelo.
2. **Confusión de prendas:** Una chaqueta común de color llamativo fue detectada como `vest`. *Por qué:* El modelo se está guiando más por la intensidad del color que por las bandas reflectantes.
3. **Objetos de fondo:** Un cubo/balde en el suelo fue clasificado como `helmet`. *Por qué:* Forma geométrica circular muy similar a la vista superior de un casco.

## Falsos Negativos (FN) identificados
1. **Oclusión severa:** Un trabajador detrás de un andamio no fue detectado (`person`) y tampoco sus EPIs. *Por qué:* Más del 70% de su cuerpo estaba tapado por tubos metálicos.
2. **Escala pequeña:** No se detectó un `security shoe` en un trabajador lejano. *Por qué:* Al redimensionar la imagen a 640x640, los píxeles que conforman el zapato se pierden.
3. **Bajo contraste:** No se detectó un `harness` sobre un trabajador vestido de negro. *Por qué:* Falta de contraste de bordes que el modelo necesita para separar el objeto del fondo.

## Mejoras Prioritarias de Datos (Plan de Iteración)
1. **Aumento de datos (Data Augmentation):** Aplicar variaciones de brillo y contraste extremas en Roboflow para enseñar al modelo a detectar arneses en condiciones de sombra/bajo contraste.
2. **Etiquetado de oclusiones:** Buscar y etiquetar específicamente fotos de trabajadores operando detrás de mallas, andamios o maquinaria (casos límite).
3. **Imágenes de fondo (Backgrounds):** Añadir al dataset un 10% de imágenes sin trabajadores pero con elementos de obra (cubos, conos, vallas) sin etiquetar nada, para obligar al modelo a reducir sus Falsos Positivos.
