## Análisis estadístico general a un dataframe

- `df.info()`: arroja conteo de no nulos y tipo de datos, por columna.

- `df.describe()`: arroja resumen de estadísticas para las columnas de tipo numérico. (desviación estandar, media, cuartiles, conteo, mínimo, máximo)

## Transformación de tipo de datos
Las fechas son más útiles en formato de serie de tiempo. Para transformar fechas de formato de texto a serie de tiempo puede usarse el comando `pd.to_datetime()`. Luego se pueden extraer por separado sus componentes:
```python
data['año'] = data['invoice date'].dt.year
data['mes'] = data['invoice date'].dt.month
# Día y hora: aplican el mismo patrón con .dt.day y .dt.hour
```

## Limpieza de datos
Se pueden eliminar duplicados y valores vacíos o nulos.

## Creación de columnas nuevas
Se pueden crear columnas nuevas con información de interés a partir de columnas existentes. Por ejemplo `cantidad_total = cantidad * precio`. También podría calcular una columna llamada `semestre` dependiendo del mes de la fecha (1 a 6 o 7 a 12, primer semestre o segundo semestre).

## Agrupar y resumir datos
Se puede usar `groupby` para generar tablas resumen. 

## Resumir datos usando gráficos
- Gráfico de pastel: ventas, devoluciones.
- Gráfico de barras: ventas por mes, a lo largo del año o periodo deseado.