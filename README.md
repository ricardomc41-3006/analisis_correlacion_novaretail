🛒 Análisis Correlacional y Drivers de Ingresos: NovaRetail+

🎯 Objetivo del Proyecto

Evaluar los factores del comportamiento del cliente que presentan una mayor asociación con el ingreso anual generado en NovaRetail+, una plataforma de comercio electrónico en Latinoamérica. A través de un análisis exploratorio y correlacional sobre 15,000 usuarios (cierre 2024), se busca brindar evidencia estadística al equipo de Crecimiento y Retención para priorizar iniciativas comerciales, entendiendo que correlación no implica causalidad.

📁 Conjunto de Datos Utilizado

El estudio se realiza sobre el dataset novaretail_comportamiento_clientes_2024.csv (15,000 registros y 12 columnas, sin valores nulos), que integra variables demográficas, de comportamiento y métricas de negocio:

Identificación y demografía: id_cliente, edad, nivel_ingreso, region, tipo_dispositivo.

Comportamiento y marketing: visitas_mes, compras_mes, gasto_publicidad_dirigida, satisfaccion.

Suscripción, retención e ingresos: miembro_premium (binaria), abandono (binaria) e ingreso_anual (métrica principal).

🛠️ Etapas del Análisis Realizadas

Carga, Exploración y Tipificación (EDA): Revisión de estructura, estadísticas descriptivas de variables numéricas, binarias y categóricas, y corrección del tipo de dato en edad (float64 a int64).

Visualización de Relaciones: Generación de un mapa de calor global (Heatmap) para detectar asociaciones lineales y gráficos de dispersión (Scatterplots) individuales enfocados en los pares más relevantes respecto a ingreso_anual.

Evidencia Numérica y Coeficientes Estadísticos:

Pearson y Spearman: Evaluación de relaciones lineales y monótonas entre variables numéricas (ingreso_anual, compras_mes, visitas_mes).

Punto-biserial: Medición de la asociación entre variables binarias (miembro_premium, abandono) e ingreso_anual.

V de Cramér: Implementación de una función reutilizable (cramers_v) para cuantificar la asociación en 5 pares clave de variables categóricas y binarias.

Interpretación de Negocio y Próximos Pasos: Traducción de hallazgos estadísticos en implicaciones comerciales, identificación de limitaciones del estudio (estacionalidad e historial del cliente) y propuesta de experimentos A/B y análisis por cohortes.

💡 Hallazgos Clave

Frecuencia de compras y colinealidad: compras_mes e ingreso_anual presentan una correlación positiva casi perfecta (0.97 en Pearson y Spearman), comportándose prácticamente como la misma señal económica.

Fricción en el embudo de conversión: Las visitas mensuales (visitas_mes) muestran una relación positiva moderada-débil con los ingresos (0.34 en Pearson; 0.32 en Spearman) y alta dispersión, revelando un segmento de usuarios con alto tráfico pero nula o baja conversión.

Desempeño del programa Premium: Tener suscripción Premium muestra una asociación casi nula con el gasto anual directo (Punto-biserial de 0.09), pero destaca como la única variable categórica/binaria con una relación relevante frente a una menor tasa de abandono (V de Cramér de 0.1202). Esto sugiere que aporta valor en retención, pero requiere rediseñar sus beneficios para impulsar el ticket anual.

Independencia geográfica y de dispositivo: Los cruces entre region, tipo_dispositivo y abandono arrojaron valores de V de Cramér cercanos a 0.01, descartando sesgos operativos por región o canal.

🚀 Cómo ejecutar el Notebook (Guía de Reproducción)

Requisitos previos

Python 3.8 o superior.

Librerías: pandas, numpy, matplotlib, seaborn, scipy.

Ejecución:

1. Clona este repositorio: git clone https://github.com/ricardomc41-3006/analisis-correlacion-novaretail.git

2. Asegúrate de tener el archivo novaretail_comportamiento_clientes_2024.csv en la ruta configurada (o ajusta la ruta de lectura en la celda de carga de datos).

3. Abre el archivo analisis_novaretail.ipynb en Jupyter Notebook o Google Colab.

4. Ejecuta las celdas secuencialmente de arriba hacia abajo para replicar el análisis y las visualizaciones.
