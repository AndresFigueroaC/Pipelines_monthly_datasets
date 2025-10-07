# 🛰️ Conversión de Datos Climáticos Satelitales a Series Mensuales por Unidad Administrativa (Perú)

Este repositorio contiene scripts en **Python** que procesan y convierten datos satelitales rasterizados en **promedios mensuales por departamento, provincia y distrito del Perú**, exportando los resultados en formato **Excel (.xlsx)** listos para análisis geoespacial, ambiental o estadístico.

---

## 📊 Variables Climáticas Utilizadas

| Variable | Fuente / Base de Datos | Periodo | Descripción |
|-----------|------------------------|----------|--------------|
| 🌧️ **Precipitación (CHIRPS)** | Climate Hazards Group InfraRed Precipitation with Station Data | 1981–2025 | Datos mensuales globales de precipitación derivados de estaciones y satélite. |
| 🌡️ **Land Surface Temperature (MODIS)** | NASA MOD11A2 / MYD11A2 (8-day composite) | 2000–2025 | Temperatura superficial terrestre (LST) derivada de sensores MODIS. |
| 🟡 **Dióxido de Nitrógeno (NO₂)** | ACAG (Washington University) | 2018–2024 | Estimaciones globales de NO₂ derivadas de modelos y observaciones satelitales. |
| ⚫ **Material Particulado Fino (PM₂.₅)** | SatPM2.5 (ACAG, Washington University, versión V6.GL.02.04) | 2018–2024 | Estimaciones globales de PM₂.₅ basadas en datos satelitales, modelos y observaciones terrestres. |

---

## 📂 Estructura de Datos

Los archivos de entrada incluyen datos rasterizados (.tif, .nc) almacenados localmente o en repositorios externos.  
> 📁 Carpeta Drive con datos LST (MODIS):  
> [🔗 Acceder aquí](https://drive.google.com/drive/folders/1pZ-qK9C0nG9ZKX6e3JdvHxWpMOFAsvCz?usp=sharing)

Los demás datasets se encuentran en almacenamiento local (≈100 GB), debido a su tamaño.

---

## ⚙️ Funcionalidad Principal

Los scripts del repositorio permiten:

1. Leer y combinar datos raster satelitales multitemporales.  
2. Calcular promedios mensuales por límites administrativos (departamento, provincia, distrito).  
3. Exportar resultados en formato **Excel (.xlsx)** y **CSV** para análisis posterior.  
4. Generar salidas listas para visualización o integración con sistemas SIG.  

---

## 🧩 Tecnologías Utilizadas

- Python ≥ 3.9  
- Rasterio  
- Geopandas  
- Xarray  
- Numpy / Pandas  
- Matplotlib (opcional para visualización)

---

## 🚀 Ejemplo de Flujo

```python
# 1. Definir rutas
data_path = r"D:\Datos\MODIS_LST"
output_path = r"D:\Resultados\LST_Promedios"

# 2. Ejecutar script principal
python generar_promedios_mensuales.py

# 3. Salida esperada
# -> LST_mensual_departamental.xlsx
# -> LST_mensual_provincial.xlsx
# -> LST_mensual_distrital.xlsx
