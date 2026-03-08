# Prototipo: Detección de EPIs en Obras

## Entregables (Parte B)
* [Presentación de Diapositivas (PDF)](docs/Presentacion_Leonardo_Freitez.pdf)
* [Mini-Informe Ejecutivo (PDF)](docs/Mini_Informe_Leonardo_Freitez.pdf)

## 1. Planteamiento del Problema y Criterios de Éxito
**Problema:** En las obras de construcción, el incumplimiento del uso de Equipos de Protección Individual (EPIs) es una causa crítica de accidentes. Este proyecto busca automatizar el la deteccion visual de trabajadores para detectar si portan correctamente sus equipos de seguridad, reduciendo el trabajo manual del supervisor de prevención.
**Criterio de éxito:** Lograr un modelo con un *Recall* alto que minimice los Falsos Negativos (evitar que un trabajador desprotegido pase desapercibido).

## 2. Definición de Clases y Reglas de Etiquetado
* `person`: Trabajador en la obra.
* `helmet`: Casco de seguridad en la cabeza.
* `no helmet`: Cabeza visible sin casco de protección.
* `vest`: Chaleco reflectante de alta visibilidad.
* `no vest`: Torso de trabajador sin chaleco reflectante.
* `harness`: Arnés de seguridad para trabajos en altura.
* `security shoe`: Calzado de seguridad industrial.

## 3. Dataset
* **Enlace a Roboflow:** https://app.roboflow.com/leonardos-workspace-lqb8a/maic_m4t3_epis/models
* **Derechos del Dataset:** Dataset construido con fines académicos. Contiene imágenes públicas y/o de uso interno bajo fair-use educativo.
* **Split de datos:** 70% Train Set / 20% Valid Set / 10% Test Set.

## 4. Resumen de Resultados
* **Precisión (P):** 0.855  
* **Recall (R):** 0.44
* **mAP50:** 0.517 (Tu nota global, 51.7%, requiere mejorar el entrenamiento).
  
**Conclusiones Clave:** 1. El modelo tiene una alta Precisión (85.5%), es decir, cuando detecta un EPI, es muy confiable.
2. El Recall es bajo (44%), indicando que a la IA le cuesta encontrar *todos* los EPIs presentes, probablemente debido a oclusión o tamaño pequeño de objetos (como los zapatos).
3. Las clases `helmet` y `person` tienen el mejor rendimiento, mientras que `harness` necesita más volumen de datos.

## 5. Checklist de Reproducibilidad
* **Versión del dataset:** v1 (Roboflow Export YOLOv26)
* **Variante del modelo:** `yolo26l.pt` (Large)
* **Parámetros:** Epochs: 50 / Batch: 16 (Auto) / Imgsz: 640
* **Versión de librería:** `ultralytics 8.4.21`

## 6. Prueba de Reproducibilidad (Cómo ejecutar)
1. Abre el repositorio y dirígete a la carpeta `/notebooks/`.
2. Abre el archivo `.ipynb` utilizando **Google Colab**.
3. Asegúrate de tener activa una GPU (Entorno de ejecución > Cambiar tipo > T4 GPU).
4. Reinicia el entorno y ejecuta todas las celdas de forma secuencial.
5. *Nota:* El código descarga automáticamente el dataset mediante API.
* **Última ejecución exitosa:** Marzo 2026.
* **Hardware utilizado:** T4 GPU (Google Colab).
* **Tiempo esperado de ejecución:** ~8-10 minutos para 50 épocas.

*Nota: Para hacer inferencia directa sin re-entrenar, puedes cargar los pesos finales `best.pt` (https://drive.google.com/file/d/1EanaeFfON11RuZutVJDshCXtro5696O5/view?usp=sharing)*
