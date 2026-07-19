# Jupyter

## Comandos mágicos en Jupyter Notebooks

Dentro de un Jupyter notebook, se pueden escribir comandos mágicos. Estos permmiten ejecutar acciones de directorios o tiempos de ejecución o archivos, dentro del notebook, y así acortar tiempos de trabajo. Permiten interactuar con el sistema operativo y entornos virtuales.

`%ls` ➡ lista archivos del directorio actual
`%pwd` ➡ muestra ruta al directorio actual

**Tiempo de ejecución:**
* `%time` retorna el tiempo de ejecución de una linea de comando. Ejemplo:  `%time sum([x for x in range(10000)])`
* `%%time` evalua el tiempo de una celda completa. Se escribe al inicio de la celda.
* `%timeit` ejemplo:
```python
%timeit
result = []
for i in range(10000):
    result.append(i**2)
```

`%whos` información sobre variables activas.

Escribir a archivo:

```python
    %%writefile file.py
    print('Este código fue guardado en un archivo')
```

Ejecutar archivo:

```python
    %run file.py
```

`%matplotlib inline` se escribe al inicio de una celda en la cual se va a crear un gráfico de matplotlib, y así el gráfico aparecerá a continuación.

`%reset` ➡ borrar variables en memoria.

## Control de versiones para notebooks

Para trabajar con git y github en proyectos con jupyter notebooks, se usa el paquete nbdime (se debe instalar en el entorno virtual, puede ser con `conda install nbdime`). Así se instalará en el entorno activo de conda. Los archivos de notebooks no están basados en formato de texto, ya que están basados en archivos de tipo json. Por eso no es posible ver los contenidos y cambios en un simple editor de texto.

`nbdime config-git --enable`
`nbdiff ejemplo.ipynb ejemplo2.ipynb` comparar diferencias entre 2 notebooks.

¿Cómo fusionar cambios con `nbmerge`?

Cuando dos desarrolladores trabajan sobre la misma notebook y Git detecta un conflicto, nbdime ofrece el comando nbmerge para fusionar los cambios. Este proceso requiere tres archivos:

* Un archivo base (la versión original).
* El archivo con los cambios del primer desarrollador.
* El archivo con los cambios del segundo desarrollador.
`cp ejemplo.ipynb base.ipynb`
`nbmerge base.ipynb ejemplo.ipynb ejemplo2.ipynb -o resultado_fusion.ipynb`

El parámetro -o permite guardar el resultado en un nuevo archivo. Así obtienes una notebook fusionada sin necesidad de resolver manualmente el JSON.