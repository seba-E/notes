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
`conda env export > my_env.yaml` ➡ exportar entorno a archivo yaml
`bash conda env create -f my_env.yaml` ➡ crear entorno a partir del archivo yaml
`conda env update -f env.yaml` ➡ agregar librerías de archivo yaml al entorno activo.