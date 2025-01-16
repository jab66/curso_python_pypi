# Calculadora

Este proyecto tiene como objetivo la creación de una librería en Python que tiene los siguientes métodos:

- Suma
- Resta
- División
- Multiplicación

### Pasos a seguir par la publicacion de paquetes

- Sitio de PyPi: pypi.org
- Hay que estar registrado
- Instalar
  - setuptools wheel twine
- Obtener desde el sitio choosealicense.com la licencia free ( GNU GPLv3 )
- Crear el archivo LICENSE
- Crear el archivo README.md
- Crear el archivo setup.py
- Pasos para publicar el paquete:
  - sdist = source distribution
  - bdist = build distribution
  - python setup.py sdist bdist_wheel
  - se crean los empaquetados build y dist
  - en dist ha creado un archivo con extension tar.gz
- Pasos para subir el paquete:
  - twine upload dist/*
  - proveer el token correspondiente
- Instalar el paquete
  - pip install calculin

IMPORTANTE: cuando se hace una nueva version de la libreria, elimnar los directorios:
- build
- [nombre_paquete].egg-info
- dist

operacion.py
```python
def suma(a, b):
    return a+b

def resta(a, b):
    return a-b

def divide(a, b):
    return a/b

def multiplica(a, b):
    return a*b
```


setup.py
```python
import setuptools
from pathlib import Path

long_desc = Path("description").read_text(encoding="utf-8")

setuptools.setup(
    name="calculin",
    version="0.0.5",
    long_description=long_desc,
    packages=setuptools.find_packages(
        exclude=["codes"]
    )
)
```

En Curso_Python se encuentra el paquete pypi-test que contiene el archivo app.py donde se puede ver como importarla y acceder a cada uno de sus métodos.

```python
from calculin import operacion

print(operacion.suma(5, 10))
print(operacion.divide(5, 10))
print(operacion.multiplica(5, 10))
print(operacion.resta(5, 10))
```