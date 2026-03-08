# Análisis de Errores - Detección de EPIs

## Falsos Positivos (3 ejemplos identificados)
1. **Confusión de color:** El modelo identificó una mochila amarilla fluorescente como si fuera un `vest` (chaleco reflectante).
2. **Formas similares:** Un cubo de plástico redondo y blanco en el suelo fue clasificado erróneamente como un `helmet` (casco).
3. **Texturas:** Una bota de calle oscura fue clasificada como `security shoe` al confundirse por la iluminación deficiente.

## Falsos Negativos (3 ejemplos identificados)
1. **Oclusión parcial:** El modelo no detectó el `harness` (arnés) de un trabajador porque estaba de perfil y el arnés quedaba parcialmente oculto por su brazo.
2. **Falta de contraste:** No se detectó un `helmet` oscuro porque el trabajador estaba en una zona de sombra densa en la obra.
3. **Distancia:** Un trabajador (`person`) muy al fondo de la imagen no fue detectado por la resolución y la lejanía.

## Plan de Mejora Prioritaria (Iteración de datos)
1. Añadir imágenes al dataset donde haya trabajadores parcialmente ocultos por andamios o maquinaria (oclusión).
2. Incluir fotografías tomadas en condiciones de baja iluminación y alto contraste (sombras duras) para mejorar la robustez.
3. Incorporar imágenes de "fondo negativo" que contengan objetos redondos o fluorescentes que NO sean EPIs, para enseñarle al modelo a no confundirlos.
