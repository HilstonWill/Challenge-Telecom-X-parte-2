Predicción de Cancelación de Clientes – Telecom X (Parte 2)

Este repositorio contiene una reproducción simplificada del desafío de análisis y predicción de churn (cancelación de clientes) para una compañía de telecomunicaciones. El objetivo es construir modelos que permitan anticipar qué clientes tienen mayor probabilidad de cancelar sus servicios y, a partir de ello, sugerir estrategias de retención.

Introducción

El conjunto de datos original del desafío (WA_Fn‑UseC_‑Telco‑Customer‑Churn.csv) reúne información demográfica, de servicios contratados y de facturación mensual de alrededor de 7 000 clientes. Debido a restricciones de acceso en este entorno, en el notebook Challenge‑Telecom‑X‑parte‑2.ipynb se genera un conjunto de datos sintético con características y proporciones de cancelación similares al original. No obstante, la metodología de limpieza, exploración, modelado y evaluación es idéntica y puede aplicarse al fichero real si se dispone de él.

Contenido del proyecto

El análisis sigue la siguiente estructura:

Limpieza y preprocesamiento: eliminación de columnas irrelevantes, tratamiento de valores perdidos y codificación de variables categóricas a numéricas.

Análisis exploratorio: cálculo de la proporción de cancelaciones, visualizaciones del desequilibrio de clases y estimación de correlaciones entre variables.

Modelado predictivo:

Regresión Logística, previa normalización de las variables, por su simplicidad e interpretabilidad.

Random Forest, para capturar interacciones no lineales y obtener mayor capacidad de generalización.

Evaluación de modelos: cálculo de métricas como exactitud, precisión, exhaustividad (recall), F1‑score y área bajo la curva ROC (AUC), junto con la comparación de resultados entre modelos.

Importancia de características: identificación de las variables con mayor peso en cada modelo.

Conclusiones y recomendaciones: interpretación de los hallazgos y propuesta de acciones para retener a los clientes con mayor riesgo de cancelación.

Cómo ejecutar el notebook

Clona este repositorio en tu entorno local o en Google Colab.

Abre el notebook Challenge‑Telecom‑X‑parte‑2.ipynb en Jupyter o Colab.

Ejecuta todas las celdas para reproducir el análisis. El código generará un conjunto de datos sintético automáticamente. Si deseas usar el archivo real, coloca el CSV en la carpeta data/ y reemplaza la función make_classification por la lectura del CSV.

Explora las salidas y gráficas para comprender qué factores impulsan la cancelación y cómo se comportan los modelos.

Además del notebook, este repositorio incluye la presentación answer.pptx, que resume el flujo de trabajo y los resultados principales en forma de diapositivas profesionales, así como el script de generación de la presentación con PptxGenJS (generate_presentation.js).

Resultados principales

Los clientes con facturas mensuales altas y poca antigüedad presentan una mayor probabilidad de cancelar sus servicios, ya que a un alto coste en un periodo corto de contrato corresponde un menor cargo total acumulado.

Los modelos estudiados muestran que la Regresión Logística ofrece interpretabilidad y una exactitud aceptable (~0,75 en el conjunto sintético), mientras que el Random Forest consigue mayor rendimiento global (AUC cerca de 0,83) al capturar relaciones no lineales.

Las variables más influyentes en el riesgo de churn son el tenure (tiempo de relación con la empresa), el MonthlyCharges y el TotalCharges.

Se recomiendan estrategias de retención orientadas a los segmentos de clientes con poco tiempo de contrato y altas facturas mensuales, como ofrecer descuentos o planes más ajustados, mejorar la atención al cliente y proporcionar incentivos de permanencia.

Referencias

Las conclusiones de este análisis se apoyan en fuentes públicas sobre modelos de predicción de churn y comparación de algoritmos. Por ejemplo, un estudio de Analytics Vidhya destaca que los clientes con facturación mensual alta y baja antigüedad tienen mayor riesgo de cancelar. Otro artículo de MarketR indica que, para conjuntos de datos de churn, la regresión logística obtiene aproximadamente 81,5 % de exactitud y que los Random Forest logran un desempeño similar o superior con mejor manejo de interacciones no lineales.
