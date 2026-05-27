#  Análisis Exploratorio de Vuelos NYC 2013
[Ver reporte interactivo](https://adrian-mtz03.github.io/analisis-vuelos-nyc-2013/)
**Autor:** Guillermo Adrian Martinez Vanegas  
**Herramientas:** R · dplyr · SQL · SQLite · ggplot2 · Quarto  
**Dataset:** `nycflights13` — 336,776 vuelos desde los aeropuertos de Nueva York

---

##  Descripción

Análisis exploratorio de datos del dataset `nycflights13`, que registra todos los vuelos comerciales que partieron desde los tres aeropuertos de Nueva York (JFK, LGA y EWR) durante 2013.

Cada una de las 20 preguntas analíticas se responde con **dos implementaciones paralelas**: una usando el ecosistema `dplyr` de R y otra con consultas `SQL` sobre una base de datos SQLite, permitiendo validar resultados cruzados y demostrar dominio de ambas herramientas.

La decisión metodológica central del análisis fue **filtrar únicamente los retrasos efectivos** (`delay > 0`), descartando valores negativos (salidas anticipadas) para medir la magnitud real de los retrasos en lugar de un balance neto.

---

##  Tecnologías utilizadas

| Herramienta | Uso |
|---|---|
| R | Lenguaje principal de análisis |
| dplyr | Manipulación y transformación de datos |
| SQL + SQLite | Consultas relacionales sobre el dataset |
| DBI / RSQLite | Conexión entre R y la base de datos |
| ggplot2 | Visualizaciones estadísticas |
| lubridate | Manejo de fechas |
| Quarto | Documento reproducible HTML |

---

##  Preguntas analizadas

| # | Pregunta |
|---|---|
| 1 | ¿Qué aerolínea tuvo el mayor retraso promedio en la salida en 2013? |
| 2 | ¿Qué día de la semana tuvo más vuelos retrasados en promedio? |
| 3 | ¿Cuál es la distribución de los retrasos en la salida para cada aeropuerto? |
| 4 | ¿Qué proporción de vuelos se retrasaron más de 30 minutos? |
| 5 | ¿Qué destinos tuvieron los mayores retrasos promedio en la llegada? |
| 6 | ¿Qué aerolíneas tuvieron el mayor número de vuelos desde NYC? |
| 7 | ¿Cómo varía el retraso de los vuelos según el fabricante de la aeronave? |
| 8 | ¿Los aviones más antiguos tienen más retrasos? |
| 9 | ¿Qué modelos de aviones se utilizan con mayor frecuencia en vuelos desde NYC? |
| 10 | ¿Cuál es la distancia promedio de vuelo por aerolínea? |
| 11 | ¿Qué aeropuerto de NYC tuvo el mayor número de retrasos en la salida? |
| 12 | ¿Qué aeropuerto tuvo el menor tiempo promedio de taxi-out? |
| 13 | ¿Qué porcentaje de vuelos que salen de cada aeropuerto de NYC fueron puntuales? |
| 14 | ¿Qué aeropuertos de destino tienen el mayor retraso promedio en la llegada? |
| 15 | ¿Cómo varían los retrasos en la salida según la hora del día en cada aeropuerto? |
| 16 | ¿Cuál es la correlación entre la velocidad del viento y los retrasos en la salida? |
| 17 | ¿Los vuelos experimentan más retrasos en días con lluvias intensas? |
| 18 | ¿Cómo afecta la temperatura a los retrasos de los vuelos? |
| 19 | ¿Cómo afectan los niveles de visibilidad a los retrasos en la llegada? |
| 20 | ¿La alta humedad se relaciona con los tiempos de taxi-out más largos? |

---

##  Visualizaciones incluidas

- **Violin plot** con escala logarítmica — distribución de retrasos por aeropuerto
- **Bubble chart** — relación entre antigüedad del avión y retraso promedio
- **Bar chart** — impacto de la temperatura en los retrasos operativos
- **Line chart** — evolución del retraso a lo largo del día por aeropuerto
- **Horizontal bar chart** — top 10 aeropuertos destino con mayores demoras

---

##  Hallazgos principales

- **SkyWest Airlines** registró el mayor retraso promedio de salida en 2013
- El **jueves** es el día con más vuelos retrasados en promedio
- **LaGuardia (LGA)** es el aeropuerto más puntual; **Newark (EWR)** el menos puntual
- Casi el **15%** de los vuelos se retrasaron más de 30 minutos
- El **clima caliente (≥ 80°F)** genera más retrasos que el frío, contrario a la intuición
- La **visibilidad crítica (< 2 millas)** casi duplica el retraso promedio de llegada
- La **humedad alta** se asocia positivamente con tiempos de taxi-out más largos
- El **año de fabricación** del avión tiene una correlación casi nula con los retrasos

---

##  Estructura del repositorio

```
 analisis-vuelos-nyc
├── Proyecto_primera_parte.qmd   # Código fuente Quarto
├── Proyecto_primera_parte.html  # Reporte renderizado
├── vuelos.db                    # Base de datos SQLite
└── README.md                    # Este archivo
```

---

##  Cómo reproducir el análisis

1. Clona el repositorio:
```bash
git clone https://github.com/tu-usuario/analisis-vuelos-nyc.git
```

2. Abre `Proyecto_primera_parte.qmd` en RStudio

3. Instala las dependencias necesarias:
```r
install.packages(c("DBI", "RSQLite", "dplyr", "ggplot2", "lubridate", "knitr"))
```

4. Renderiza el documento:
```bash
quarto render Proyecto_primera_parte.qmd
```

---

## 📬 Contacto

**Guillermo Adrian Martinez Vanegas**  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/tu-usuario)
[![GitHub](https://img.shields.io/badge/GitHub-black?style=flat&logo=github)](https://github.com/tu-usuario)
