# Entornos virtuales con Python

## Entornos virtuales tipo venv

A los entornos virtuales venv les llamaremos **venv**, como abreviación.

### Crear un venv en la terminal de windows

Navegar al directorio donde se quiere crear el venv. Luego usar el comando:
`python3 -m venv my_venv`

### Activar el venv en la terminal

En la terminal de windows, usar el siguiente comando:
`my_venv\Scripts\activate`

### Desactivar el venv en la terminal

Escribir el comando `deactivate`.

## Anaconda

In your regular powershell you can run the commands.

### Create an environment

`conda create --name my_env python=3.5`
`conda activate my_env`
`conda env list`

### Remove an environment

`conda remove -n my_env --all` ➡ curso Platzi
`conda env remove --name my_env` ➡ conda cheatsheet

### Manage packages

`conda install jupyter pandas scikit-learn` ➡ instalar paquetes en el entorno activo
`conda list` ➡ listar paquetes instalados en el entorno activo
`conda remove pandas` ➡ elimina paquete del entorno activo
`conda remove --name my_env numpy pandas` ➡ eliminar paquetes de un entorno específico.
`conda clean --packages` ➡ limpiar parcialmente la cache
`conda clean --all` ➡ limpiar completamente la cache
`conda update scikit-learn` ➡ actualizar paquete específico en el entorno activo
`conda update --all` ➡ actualizar todos los paquetes del entorno activo
`conda create --clone my_env --name my_env_2` ➡ crear copia exacta de un entorno específico
`conda env export > my_env.yml` ➡ exportar entorno a archivo yml
`cat my_env.yml` ➡ genera informe de texto sobre el contenido del archivo yml.
`bash conda env create -f my_env.yml` ➡ crear entorno a partir del archivo yml.
`conda env update -f env.yml` ➡ agregar librerías de archivo yml al entorno activo.

### Canales en conda

¿Qué es un canal en Conda y por qué es importante?

En el mundo del software y, en particular, de la gestión de paquetes, el concepto de "canal" es fundamental. En el contexto de Conda, un canal es un repositorio de paquetes de software. Conda utiliza estos repositorios para buscar, instalar y actualizar bibliotecas. Los canales no solo determinan la disponibilidad de un paquete, sino también qué tan actualizado está. Entender cómo funcionan y cómo priorizarlos puede mejorar significativamente tu flujo de trabajo.

¿Cuáles son los principales canales en Conda?

1. **Default**: canal oficial operado por Anaconda Inc. Privilegia estabilidad y soporte probado.
2. **Conda Forge**: canal operado por la comunidad, lo que permite que se actualicen rápidamente los paquetes.

`conda config --add channels conda-forge` agregar conda-forge a mis canales disponibles configurados.
`conda install -c conda-forge bokeh` ejemplo instalar paquete bokeh desde conda-forge.
`conda config --show channels` muestra canales disponibles configurados y su orden de prioridad.
`conda config --set channel_priority strict` ajusta configuración de prioridades a estricta.
`conda install numpy pandas matplotlib -c conda-forge` ejemplo, instalar paquetes desde conda-forge.

## Cookiecutter

Herramienta para estructurar proyectos de ciencia de datos y machine learning.

```python
# Comando de instalación típico en Conda
conda install -c conda-forge cookiecutter
# Comenzar nuevo proyecto (usando versión antigua v1)
ccds https://github.com/drivendataorg/cookiecutter-data-science -c v1
```

### Hooks para automatizar tareas en cookiecutter

¿Qué son los hooks y qué tipos existen en Cookie Cutter?

Los hooks son scripts en Python que se ejecutan de forma automática durante el proceso de generación de un proyecto con Cookie Cutter. Su propósito es automatizar configuraciones que normalmente se harían de forma manual, lo que garantiza consistencia entre proyectos.

Existen dos tipos principales:

**Pre-hook (pre_gen_project.py)**: se ejecuta antes de generar el proyecto. Es útil para validar la entrada del usuario o preparar configuraciones previas.
**Post-hook (post_gen_project.py)**: se ejecuta después de generar el proyecto. Sirve para automatizar tareas como inicializar Git, crear entornos virtuales o instalar dependencias.

Ambos archivos deben ubicarse dentro de una carpeta llamada hooks en la raíz de la plantilla, al mismo nivel que el archivo cookiecutter.json y el directorio del proyecto.
