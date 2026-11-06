# Análisis de Movilidad Urbana y Economía - Ciudades Latinoamericanas

Análisis realizado durante el Sprint 5 sobre la relación entre la movilidad urbana y los indicadores económicos de ciudades latinoamericanas.

El proyecto integra datos de tráfico urbano de TomTom con indicadores económicos y sociales de OECD, con el propósito de identificar patrones entre la congestión vehicular, los tiempos de viaje y la productividad económica medida mediante el PIB per cápita.

## 📂 Contenido del repositorio
- `mobility_economy_project_student.ipynb` → Notebook principal con la exploración, limpieza, transformación, agregación, integración, visualización y conclusiones del proyecto.

> Nota: Los datasets utilizados dentro del notebook son `tomtom_traffic.csv` (TomTom) y `oecd_city_economy.csv` (OECD). El dataset final generado es `ladb_mobility_economy_2024_clean.csv`. Estos son los nombres de los datasets trabajados en el análisis, no son archivos separados en este repositorio.

## ▶️ Cómo abrir el notebook en Google Colab
1. Descarga el archivo `mobility_economy_project_student.ipynb`
2. Súbelo a Google Colab
3. Ejecuta las celdas en orden

## 📘 Cómo reproducir el análisis
1. Carga los datasets `tomtom_traffic.csv` y `oecd_city_economy.csv`
2. Revisa estructura, tipos de datos y valores faltantes con `.info()` y `.head()`
3. Estandariza los nombres de columnas a snake_case
4. Convierte fechas con `pd.to_datetime()` y variables numéricas a formato adecuado
5. Crea la variable `population` a partir de `population_m`
6. Extrae el año de `update_time_utc` y filtra 2024
7. Agrega los datos de tráfico por ciudad, país y año
8. Integra con unión INNER por `city` y `year`
9. Genera visualizaciones y analiza patrones
10. Exporta el resultado como `ladb_mobility_economy_2024_clean.csv`

## 🧠 Objetivo del análisis
Analizar la posible relación entre movilidad urbana y productividad económica en ciudades latinoamericanas:
- Identificar patrones de congestión vehicular
- Analizar tiempos de viaje y retrasos por tráfico
- Comparar indicadores de movilidad con PIB per cápita
- Identificar ciudades con comportamientos atípicos
- Evaluar si existe relación entre mayor congestión y menor productividad

## 📊 Principales análisis realizados
- **Congestión:** `jams_delay`, `traffic_index_live`, `jams_length_in_kms`, `jams_count`
- **Retrasos:** `mins_delay`
- **Tiempos de viaje:** `travel_time_live_per_10kms_mins` vs `travel_time_hist_per_10kms_mins`
- **Productividad:** `city_gdp_per_capita`
- **Desempleo:** `unemployment_pct`
- **Calidad ambiental:** `pm25`
- **Población:** `population`
- Comparación entre ciudades latinoamericanas con indicadores consolidados para 2024

## 📈 Visualizaciones
- Boxplot de `jams_delay` para distribución, mediana y atípicos
- Histograma de `city_gdp_per_capita` para distribución del PIB per cápita
- Gráfico de barras por ciudad para comparar congestión y productividad

## 🔎 Principales hallazgos
Análisis de 15 ciudades latinoamericanas durante 2024, con datos de TomTom y OECD.

- **Ciudad de México (CDMX)** es un caso atípico en congestión, con aproximadamente 2,833 minutos de `jams_delay`. Requiere especial atención y validación.
- **Montevideo** funciona como contracaso: PIB per cápita elevado y niveles relativamente bajos de tráfico, lo que muestra que no hay una relación lineal simple entre productividad y congestión.

## 💡 Recomendación
**Bogotá** se identifica como ciudad prioritaria para profundizar el análisis e inversión en infraestructura. Presenta aproximadamente 1,142 minutos de congestión junto con un PIB per cápita cercano a 11,442.

Estos resultados deben interpretarse como asociaciones y no como relaciones causales. Se recomienda complementar con densidad urbana, infraestructura vial, transporte público, población y evolución temporal antes de tomar decisiones de inversión.

## 🛠️ Herramientas
Python, Jupyter / Google Colab, Pandas, NumPy, Matplotlib / Seaborn

## 👩‍💻 Autora
Elia Torres - Ingeniera Bioquímica en transición a Análisis de Datos





