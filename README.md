# Prototipo: Detección de EPIs en Obras

## Planteamiento del Problema
En el sector de la construcción, la falta de Equipos de Protección Individual (EPIs) es una de las principales causas de accidentes graves. Este proyecto entrena un modelo de Visión Computacional para auditar visualmente el cumplimiento de normativas de seguridad en tiempo real.

**Clases detectadas:** `helmet` (casco), `harness` (arnés), `vest` (chaleco), `security shoe` (calzado de seguridad), `person` (persona).

**Enlace al Dataset (Roboflow):** https://app.roboflow.com/leonardos-workspace-lqb8a/maic_m4t3_epis/models
**Split de datos:** 70% Train Set / 20% Valid Set / 10% Test Set.

## Resumen de Resultados
*(Revisar la imagen `results.png` en la carpeta de evidencias para mayor detalle)*
* **Precisión (P):** 0.801  (Significa que cuando la IA dice que hay un objeto, acierta el 80.1% de las veces).
* **Recall (R):** 0.494 (Significa que logró encontrar el 49.4% de todos los objetos reales en la foto).
* **mAP50:** 0.631 (Tu nota global, 63.1%, que está súper bien para un primer prototipo de 30 épocas).

## Checklist de Reproducibilidad (Cómo ejecutar esto)
Cualquier persona puede reproducir este experimento sin instalaciones locales siguiendo estos pasos:

1. Abre el cuaderno `01_Entrenamiento_YOLO_M4T3_Tarea_LEONARDO_FREITEZ.ipynb` ubicado en la carpeta `/notebooks/` utilizando Google Colab.
2. En Google Colab, ve a *Entorno de ejecución -> Cambiar tipo de entorno* y asegúrate de seleccionar **T4 GPU**.
3. Ejecuta todas las celdas secuencialmente. El código descargará el dataset directamente desde Roboflow vía API.
4. **Parámetros utilizados:**
   * Modelo base: `yolo26s.pt` (large)
   * Epochs: 50
   * Imgsz (Resolución): 640
   * Entorno probado exitosamente con aceleración de hardware activa.

*Nota: Para hacer inferencia directa sin re-entrenar, puedes cargar los pesos finales `best.pt` (https://drive.google.com/file/d/1WpDUvikSyeKJZ_2INZaGAziRV7Vq0a2O/view?usp=sharing)*
