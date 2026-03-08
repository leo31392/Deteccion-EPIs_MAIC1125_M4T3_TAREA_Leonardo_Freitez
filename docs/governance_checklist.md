# Checklist de Gobernanza y Ética AECO

## 1. Privacidad y Consentimiento
Este modelo ha sido entrenado respetando la normativa de privacidad. Las imágenes obtenidas de fuentes públicas o en obra evitan la focalización en rostros reconocibles. No se emplean técnicas de reconocimiento facial ni extracción de datos biométricos de los trabajadores.

## 2. Minimización de Datos
El dataset se centra exclusivamente en la geometría del cuerpo (clase `person`) y la ropa/equipamiento. Cualquier información personal identificable (PII) incidental como matrículas de vehículos o rostros claros debe ser difuminada en un despliegue en producción.

## 3. Declaración de Limitaciones (Cuándo NO usar)
* **Condiciones climáticas adversas:** El modelo no ha sido probado y no garantiza resultados bajo lluvia intensa, niebla o visión nocturna sin iluminación industrial.
* **Sustitución humana:** **Bajo ninguna circunstancia** este modelo debe reemplazar al Técnico de Prevención de Riesgos Laborales. Es una herramienta de "segunda opinión" o de monitoreo estadístico, no un sistema de decisión vital autónomo.

## 4. Nota de Riesgos (FN vs FP)
En el contexto AECO, el costo de un Falso Negativo (no detectar que falta un casco) es inaceptablemente alto porque compromete vidas humanas. Sin embargo, priorizar en exceso evitar Falsos Negativos genera múltiples Falsos Positivos (alarmas falsas), lo que produce "fatiga de alarma" en los operadores, llevándolos a ignorar el sistema. Se requiere ajuste continuo del umbral de confianza según el caso de uso específico en la obra.
