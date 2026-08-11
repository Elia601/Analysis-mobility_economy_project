Este repositorio contiene el análisis realizado durante el Sprint 5 sobre la relación entre la movilidad urbana y los indicadores económicos de ciudades latinoamericanas.

El proyecto integra datos de tráfico urbano de TomTom con indicadores económicos y sociales de OECD, con el propósito de identificar patrones entre la congestión vehicular, los tiempos de viaje y la productividad económica medida mediante el PIB per cápita.

📂 Contenido del repositorio
notebooks/ladb_mobility_economy_analysis.ipynb
→ Notebook principal con la exploración, limpieza, transformación, agregación, integración, visualización y conclusiones del proyecto.
data/tomtom_traffic.csv
→ Dataset original con información de movilidad y congestión urbana.
data/oecd_city_economy.csv
→ Dataset con indicadores económicos y sociales de las ciudades.
data/ladb_mobility_economy_2024_clean.csv
→ Dataset final resultante de la integración y limpieza de los datos de movilidad y economía.
▶ Cómo abrir el notebook en Google Colab

Haz clic en el siguiente botón:

O:

Abre el archivo notebooks/ladb_mobility_economy_analysis.ipynb en GitHub.
Haz clic en Open in Colab.
Ejecuta las celdas del notebook en orden.
📘 Cómo reproducir el análisis
Abre notebooks/ladb_mobility_economy_analysis.ipynb.
Carga los datasets tomtom_traffic.csv y oecd_city_economy.csv.
Ejecuta las celdas en orden.
Revisa la estructura, tipos de datos y valores faltantes.
Estandariza los nombres de las columnas.
Convierte las fechas y variables numéricas a los formatos adecuados.
Extrae el año de los registros de tráfico y filtra el período 2024.
Agrega los datos de tráfico por ciudad, país y año.
Integra los datasets mediante una unión INNER utilizando city y year.
Genera las visualizaciones y analiza los principales patrones.
Exporta el resultado como ladb_mobility_economy_2024_clean.csv.
🧠 Objetivo del análisis

El objetivo principal es analizar la posible relación entre la movilidad urbana y la productividad económica en ciudades latinoamericanas.

Identificar patrones de congestión vehicular.
Analizar los tiempos de viaje y los retrasos asociados al tráfico.
Comparar los indicadores de movilidad con el PIB per cápita.
Identificar ciudades con comportamientos atípicos.
Evaluar si existe una relación clara entre mayor congestión y menor productividad económica.
Generar información que pueda apoyar decisiones relacionadas con infraestructura y movilidad urbana.
📊 Principales análisis realizados

El proyecto incluye análisis de:

Congestión vehicular: jams_delay, traffic_index_live, jams_length_in_kms y jams_count.
Retrasos en los desplazamientos: mins_delay.
Tiempos de viaje: comparación entre travel_time_live_per_10kms_mins y travel_time_hist_per_10kms_mins.
Productividad económica: city_gdp_per_capita.
Desempleo: unemployment_pct.
Calidad ambiental: pm25.
Población: population.
Comparación entre ciudades latinoamericanas mediante indicadores consolidados para 2024.
🧹 Proceso de limpieza y preparación

El proceso de preparación de datos incluyó:

Revisión de la estructura mediante .info() y .head().
Identificación de columnas con tipos de datos incorrectos.
Estandarización de nombres de columnas utilizando snake_case.
Conversión de las columnas de fecha de tráfico mediante pd.to_datetime().
Limpieza y conversión de indicadores económicos a valores numéricos.
Creación de la variable population a partir de population_m.
Extracción del año a partir de update_time_utc.
Filtrado de los registros correspondientes a 2024.
Agregación de las métricas de tráfico por ciudad, país y año.
Integración de movilidad y economía mediante una unión INNER.
📈 Visualizaciones

Para validar los resultados y facilitar la interpretación se utilizaron:

Boxplot de jams_delay para observar la distribución, mediana y valores atípicos.
Histograma de city_gdp_per_capita para analizar la distribución del PIB per cápita.
Gráfico de barras por ciudad para comparar indicadores de congestión y productividad económica.

Estas visualizaciones permitieron identificar patrones generales y posibles valores extremos que requieren una revisión adicional.

🔎 Principales hallazgos

El análisis corresponde a 15 ciudades latinoamericanas durante 2024, utilizando información de movilidad de TomTom e indicadores económicos de OECD.

Entre los principales resultados destaca Ciudad de México (CDMX) como un caso atípico en congestión, con aproximadamente 2,833 minutos de jams_delay, por lo que representa un punto que requiere especial atención y validación.

Por otro lado, Montevideo funciona como un contracaso relevante: presenta un PIB per cápita elevado y niveles relativamente bajos de tráfico, lo que muestra que los datos no evidencian una relación lineal simple entre productividad económica y congestión.

💡 Recomendación

A partir de los resultados iniciales, Bogotá se identifica como una ciudad prioritaria para profundizar el análisis y considerar inversiones en infraestructura de transporte. Presenta aproximadamente 1,142 minutos de congestión junto con un PIB per cápita cercano a 11,442, por lo que los datos sugieren una situación que podría beneficiarse de mejoras en movilidad.

Sin embargo, estos resultados deben interpretarse como asociaciones y no como relaciones causales. Se recomienda complementar el análisis con variables como densidad urbana, infraestructura vial, transporte público, población, crecimiento económico y evolución temporal antes de tomar decisiones de inversión.
