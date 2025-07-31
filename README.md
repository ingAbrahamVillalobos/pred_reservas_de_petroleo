Proyecto: Optimización de la Rentabilidad en la Extracción de Petróleo
Introducción
Este proyecto fue desarrollado como parte de un bootcamp de Data Scientist y se enfoca en la optimización de la selección de ubicaciones para nuevos pozos petrolíferos para la compañía OilyGiant. El objetivo principal es identificar las regiones con el mayor potencial de rentabilidad y el menor riesgo de pérdida, utilizando técnicas de aprendizaje automático y análisis estadístico.

Problema de Negocio
OilyGiant planea abrir 200 nuevos pozos petrolíferos y necesita determinar las ubicaciones más prometedoras entre tres regiones geológicas distintas. La meta es maximizar la ganancia esperada y minimizar los riesgos asociados a la inversión de $100 millones.

Metodología
El proyecto sigue un enfoque estructurado:

Análisis Exploratorio de Datos (EDA): Se realizó una inspección inicial de los datos de las tres regiones (geo_data_0.csv, geo_data_1.csv, geo_data_2.csv) para verificar la calidad de los datos (ausencia de valores nulos o duplicados) y entender las características de las reservas de petróleo.

Entrenamiento y Evaluación de Modelos:

Se implementaron modelos de Regresión Lineal para predecir el volumen de reservas en cada pozo.

Los datos de cada región se dividieron en conjuntos de entrenamiento (75%) y validación (25%).

Se calculó el volumen medio de reservas predicho y el Error Cuadrático Medio (RMSE) para cada modelo, proporcionando una métrica de la precisión de las predicciones.

Cálculo de Ganancias:

Se determinó el umbral de rentabilidad por pozo ($111.111,11 barriles) necesario para cubrir la inversión total.

Se comparó este umbral con el volumen medio de reservas reales en cada región.

Se desarrolló una función para calcular la ganancia potencial seleccionando los 200 pozos con las predicciones más altas de cada región.

Evaluación de Riesgos con Bootstrapping:

Se utilizó la técnica de bootstrapping (1000 muestras) para simular la distribución de beneficios en cada región.

Se calculó el beneficio promedio, el intervalo de confianza del 95% y la probabilidad de pérdida (ganancia negativa) para cada región.

Conclusiones y Recomendaciones
El análisis inicial de ganancias (sin riesgo) sugirió que la Región 0 presentaba la mayor ganancia esperada, lo que la posicionaría como la opción más atractiva.

Sin embargo, al incorporar la evaluación de riesgos mediante bootstrapping, se observó una situación crítica:

Todas las regiones analizadas (Región 0, Región 1, Región 2) mostraron un riesgo de pérdida del 100%. Esto significa que, bajo las condiciones de inversión ($100 millones para 200 pozos) y los ingresos por barril ($4.5), el modelo predice que la inversión inicial no se recuperará completamente en ninguna de las regiones.

Recomendación:

Basado en este análisis exhaustivo, no se recomienda proceder con la inversión en ninguna de las tres regiones propuestas bajo las condiciones actuales. La alta probabilidad de pérdida (100%) en todas las regiones indica que la inversión es inviable. Se sugiere a OilyGiant:

Reevaluar las condiciones de inversión: Explorar la posibilidad de reducir el costo por pozo o aumentar el número de barriles producidos por pozo.

Buscar nuevas regiones: Analizar datos geológicos de otras regiones que puedan ofrecer un mayor volumen de reservas y/o menor riesgo.

Revisar el precio por barril: Considerar escenarios con precios de petróleo más favorables si es posible.

Este proyecto destaca la importancia de una evaluación integral que combine la predicción de rentabilidad con un riguroso análisis de riesgos para tomar decisiones de negocio informadas.

Tecnologías Utilizadas
Python

Pandas

NumPy

Scikit-learn (LinearRegression, train_test_split, mean_squared_error)

