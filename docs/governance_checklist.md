# Checklist de Gobernanza y Privacidad (Sistemas AECO)

## Privacidad y Consentimiento
* **Minimización de datos (PII):** El conjunto de datos de imágenes se ha seleccionado evitando la captura de rostros reconocibles en primer plano. No se están recopilando datos biométricos ni matrículas de vehículos.

## Declaración de Limitaciones Críticas
* **Condiciones de fallo:** Este modelo reduce su precisión drásticamente en condiciones de baja iluminación, lluvia intensa o cuando los trabajadores están fuertemente ocluidos.
* **Descargo de responsabilidad vital:** Este sistema de IA es exclusivamente una herramienta asistiva para *screening* preliminar de seguridad. Produce Falsos Negativos. **EN NINGÚN CASO debe utilizarse como el único verificador en decisiones de seguridad vital** ni sustituir la labor del supervisor de prevención de riesgos laborales (PRL) de la obra.

## Riesgos Asociados
* **Riesgo por FP (Falso Positivo):** Generación de alertas innecesarias que pueden causar "fatiga de alarmas" en el centro de control.
* **Riesgo por FN (Falso Negativo):** Riesgo crítico donde un trabajador sin EPIs pasa desapercibido. Por esta razón, el umbral de confianza se debe ajustar priorizando el *Recall* sobre la *Precisión*.
