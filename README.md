🧩 Práctica Clase 7 – CI/CD con GitHub Actions

Materia: Metodología de Sistemas II
Profesora: Rosalía Insaurralde
Alumno/a: Paola Cabrera

🎯 Objetivo

Aplicar los conceptos de Integración Continua (CI) y Entrega Continua (CD) mediante la creación de un pipeline básico en GitHub Actions, simulando un flujo de mejora continua en un proyecto Python.

⚙️ Requisitos previos

Cuenta en GitHub

Python 3 instalado en el equipo

Un repositorio nuevo llamado PruebaCI_Cabrera

🧱 Estructura del proyecto
PruebaCI_Cabrera/
│
├── app.py
├── test_app.py
├── requirements.txt
└── .github/
    └── workflows/
        └── python-ci.yml

🧩 Descripción de los archivos

app.py
Contiene una función simple en Python:

def suma(a, b):
    return a + b


test_app.py
Incluye una prueba unitaria que valida el correcto funcionamiento de la función:

from app import suma

def test_suma():
    assert suma(2, 3) == 5


.github/workflows/python-ci.yml
Archivo de configuración del pipeline de GitHub Actions, que automatiza:

La instalación de dependencias (pytest y pytest-cov).

La ejecución de las pruebas.

El reporte de cobertura del código.

🚀 Pipeline CI en GitHub Actions

Cada vez que se hace un push al repositorio:

GitHub ejecuta el flujo definido en python-ci.yml.

Instala Python y dependencias.

Ejecuta las pruebas automáticamente.

Muestra el porcentaje de cobertura (coverage) en el log.

Ejemplo de salida esperada:
---------- coverage: platform linux, python 3.x ----------
Name     Stmts   Miss  Cover
----------------------------
app.py       2      0   100%
TOTAL        2      0   100%


✅ Si el código pasa las pruebas → el pipeline se marca como Success.
❌ Si la función está mal implementada → el pipeline falla automáticamente (alertando al desarrollador).

🔄 Ejercicio 2 – Mejora continua

Caso de error: modificar la función suma() para que devuelva a - b y observar cómo el pipeline detecta la falla.

Corrección: restaurar la suma correcta (a + b) y confirmar que el pipeline vuelve a aprobar las pruebas.

🧠 Conclusión

Esta práctica demuestra cómo la Integración Continua (CI) ayuda a:

Detectar errores rápidamente.

Garantizar la calidad del código antes de desplegar.

Implementar una cultura de mejora continua dentro del desarrollo de software.
