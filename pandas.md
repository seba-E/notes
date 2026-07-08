
## groupby
Agrupar datos según criterio.

## pivot_table
Como tablas dinámicas de excel

### Similitud de groupby y pivot_table
Hay una **intersección** entre estas funciones, es decir, cosas que se pueden hacer para obtener los mismos resultados usando cualquiera de las dos funciones. Pivot table usa groupby bajó el capó, pero con  una sintaxis similar a la de tablas dinámicas de **Excel**.

### stack and unstack
Apilar columnas como filas

## Dataframe merge
Criterios:
- inner
- outer
- left
- right

## Dataframe concat
Puede ser vertical u horizontal, según el axis especificado (0 o 1).

## Dataframe join
Apila columnas. Se une según los indices de las filas. Los criterios son:
- inner
- ...

## Dataframe info
`df.info()`, arroja el tipo de datos por columna.

## Transformar fechas
de formato texto a formato de fecha.
`df['fecha'] = pd.to_datetime(df['fecha'])`

## Set Index
Se puede cambiar los indices de fila por otros distintos a los que vienen por defecto, como por ejemplo por una serie de fechas.
`df.set_index('fecha')`

## Date range (crear rango de fechas)
```python
date_range_new = pd.date_range(start='2024-01-01', end='2024-12-31', freq='D')
# ahora ponerlo como columna en un nuevo dataframe
df_dates = pd.Dataframe(date_range_new, columns=['Date'])
```

