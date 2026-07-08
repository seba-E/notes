## Configuración inicial de librerías
```python
# install library the traditional way
pip install numpy matplotlib
# install libraries to the current python interpreter
python -m pip install numpy matplotlib

import numpy as np
import matplotlib.pyplot as plt
```

## gráfico de lineas (plot)
```python
month = np.array(['E', 'F', 'M', 'A', 'Ma'])
sales = np.array([20,25,30,28,35])

# configurar tamaño del gráfico
plt.figure(figsize=(8,6))
# crear el gráfico
plt.plot(month, sales, marker='o', color='blue')

plt.title('Ventas mensuales de un producto')
plt.xlabel('Meses')
plt.ylabel('Ventas en miles de unidades')

plt.show()
```
## grafico de dispersión (scatter)
```python
import matplotlib.pyplot as plt
# configurar tamaño del gráfico
plt.figure(figsize=(8,6))

hours = [2,3,4,5,6,7,8]
exam = [55,60,65,70,75,80,85]

plt.scatter(hours, exam, color='green')

plt.title('Relación entre horas estudiadas y puntaje')
plt.xlabel('Horas')
plt.ylabel('Puntaje')

plt.show()
```

## Gráfico personalizado
```python
import matplotlib.pyplot as plt

# configurar tamaño del gráfico
plt.figure(figsize=(8,6))

hours = [2,3,4,5,6,7,8]
exam_scores_student_1 = [55,60,65,70,75,80,85]
exam_scores_student_2 = [50,58,63,69,74,78,83]

# Crear gráfico de dispersión de dos estudiantes
plt.plot(hours, exam_scores_student_1, marker = 'o', color='green', linestyle='-', linewidth=2, label = 'Estudiante 1')
plt.plot(hours, exam_scores_student_2, marker = 's', color='red', linestyle='--', linewidth=2, label = 'Estudiante 2')

plt.title('Relación entre horas estudiadas y puntaje de dos estudiantes')
plt.xlabel('Horas')
plt.ylabel('Puntaje')

plt.legend(loc='upper left', fontsize=10, frameon=True)
# loc= Posición de la leyenda ('best', 'upper right', 'lower left', etc.)
# frameon= Mostrar o no el marco de la leyenda (True o False).

plt.show()
```