## Installing libraries in VSCode for current python interpreter

`python -m pip install numpy matplotlib`

>Good — python -m pip correctly targets the 3.14 interpreter that python actually runs. That's the fix: always install with python -m pip install ... instead of bare pip install ..., so it can't silently target the wrong environment.  

>Summary: The real issue was two different Python installs on your machine — python pointed to 3.14, pip pointed to 3.13 — so packages installed via bare pip landed in the wrong environment. Fixed by installing with python -m pip install numpy matplotlib (targets whatever python resolves to)

## Entorno virtual

Para activar: `my_venv\Scripts\activate`
donde my_venv es el nombre del entorno virtual.
Para desactivar: `deactivate`

## Empaquetar aplicación con pyinstaller

Instalar librería: `python -m pip install pyinstaller`
Ejecutar empaquetamiento(bundling): `pyinstaller main.spec`
Donde main.spec es el archivo de especificaciones para pyinstaller en el proyecto específico en que se está trabajando.