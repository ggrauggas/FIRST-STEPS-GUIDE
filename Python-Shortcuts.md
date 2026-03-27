# 🐍 Python — Guía de Referencia Rápida

> Cheatsheet práctico con todo lo esencial para empezar a programar en Python.

---

## Índice

1. [Instalación de Python](#instalación-de-python)
2. [Python en VS Code](#python-en-vs-code)
3. [Entornos Virtuales (venv)](#entornos-virtuales-venv)
4. [Hola Mundo y print()](#hola-mundo-y-print)
5. [Variables y Tipos de Datos](#variables-y-tipos-de-datos)
6. [Condicionales if / elif / else](#condicionales-if--elif--else)
7. [Bucles](#bucles)
8. [Entrada del Usuario](#entrada-del-usuario)
9. [Funciones](#funciones)
10. [Clases y POO](#clases-y-poo)
11. [Listas](#listas)
12. [Tuplas](#tuplas)
13. [Diccionarios](#diccionarios)
14. [Matrices](#matrices)
15. [Imports y pip](#imports-y-pip)
16. [Errores comunes](#errores-comunes)

---

## Instalación de Python

### Windows

1. Descarga el instalador desde [python.org/downloads](https://www.python.org/downloads/).
2. Ejecuta el instalador y **marca la casilla `Add Python to PATH`** antes de hacer clic en *Install Now*.
3. Verifica la instalación:

```bash
python --version
pip --version
```

### Linux (Ubuntu/Debian)

Python 3 suele venir preinstalado. Si no:

```bash
sudo apt update
sudo apt install python3 python3-pip python3-venv
```

Verifica:

```bash
python3 --version
pip3 --version
```

> 💡 En Linux, el comando es `python3` y `pip3`. Puedes crear un alias si quieres usar solo `python`:
> ```bash
> alias python=python3
> ```

---

## Python en VS Code

### Extensiones necesarias

| Extensión | Para qué sirve |
|---|---|
| **Python** (Microsoft) | Soporte completo: IntelliSense, linting, depuración. |
| **Pylance** | Autocompletado avanzado y análisis de tipos. |
| **Python Debugger** | Breakpoints y depuración visual. |

### Seleccionar el intérprete de Python

1. Abre la paleta de comandos: `Ctrl+Shift+P`
2. Escribe: `Python: Select Interpreter`
3. Elige la versión de Python instalada (o el entorno virtual activo).

### Ejecutar un archivo

- Botón ▶️ en la esquina superior derecha del editor.
- O desde la terminal integrada:

```bash
python archivo.py        # Windows
python3 archivo.py       # Linux / macOS
```

### Terminal integrada en VS Code

```
Ctrl + `    →  Abre/cierra la terminal
Ctrl + J    →  Muestra/oculta el panel inferior
```

---

## Entornos Virtuales (venv)

Un entorno virtual aísla las dependencias de cada proyecto. **Buena práctica: crear uno por proyecto.**

### Crear y activar en Windows

```bash
# Crear el entorno (se crea una carpeta llamada .venv)
python -m venv .venv

# Activar
.venv\Scripts\activate

# Desactivar
deactivate
```

### Crear y activar en Linux / macOS

```bash
# Crear el entorno
python3 -m venv .venv

# Activar
source .venv/bin/activate

# Desactivar
deactivate
```

### Verificar que está activo

Cuando el entorno está activo, verás su nombre al inicio del prompt:

```bash
(.venv) usuario@equipo:~/proyecto$
```

### Guardar y restaurar dependencias

```bash
# Guardar todas las dependencias instaladas en un archivo
pip freeze > requirements.txt

# Instalar dependencias desde el archivo (útil al clonar un proyecto)
pip install -r requirements.txt
```

> 💡 **En VS Code:** al abrir una carpeta con un `.venv`, VS Code lo detecta automáticamente y te pregunta si quieres usarlo como intérprete.

> ⚠️ **Añade `.venv/` a tu `.gitignore`** para no subir el entorno al repositorio.

---

## Hola Mundo y print()

```python
# El clásico
print("Hola, mundo!")

# Múltiples valores (separados por espacio por defecto)
print("Hola", "mundo", 2025)             # → Hola mundo 2025

# Cambiar el separador
print("uno", "dos", "tres", sep=" - ")   # → uno - dos - tres

# Cambiar el final de línea (por defecto es \n)
print("Sin salto", end="")
print(" de línea")                        # → Sin salto de línea

# f-strings (la forma más moderna y recomendada)
nombre = "Ana"
edad = 28
print(f"Me llamo {nombre} y tengo {edad} años.")

# Formato con expresiones dentro
precio = 9.5
print(f"Total: {precio * 2:.2f} €")      # → Total: 19.00 €
```

---

## Variables y Tipos de Datos

Python es de **tipado dinámico**: no necesitas declarar el tipo, lo infiere solo.

```python
# Tipos básicos
nombre   = "Carlos"       # str   → texto
edad     = 30             # int   → entero
altura   = 1.75           # float → decimal
es_mayor = True           # bool  → True / False
vacio    = None           # None  → ausencia de valor

# Ver el tipo de una variable
print(type(nombre))       # → <class 'str'>
print(type(edad))         # → <class 'int'>

# Conversión de tipos (casting)
numero_str = "42"
numero_int = int(numero_str)      # str → int
numero_float = float(numero_str)  # str → float
texto = str(numero_int)           # int → str

# Operadores aritméticos
print(10 + 3)    # → 13   (suma)
print(10 - 3)    # → 7    (resta)
print(10 * 3)    # → 30   (multiplicación)
print(10 / 3)    # → 3.33 (división, siempre float)
print(10 // 3)   # → 3    (división entera)
print(10 % 3)    # → 1    (módulo / resto)
print(10 ** 3)   # → 1000 (potencia)
```

---

## Condicionales if / elif / else

```python
edad = 20

if edad >= 18:
    print("Mayor de edad")
elif edad >= 16:
    print("Casi mayor de edad")
else:
    print("Menor de edad")
```

### Operadores de comparación

| Operador | Significado |
|---|---|
| `==` | Igual a |
| `!=` | Distinto de |
| `>` | Mayor que |
| `<` | Menor que |
| `>=` | Mayor o igual |
| `<=` | Menor o igual |

### Operadores lógicos

```python
# and → ambas condiciones deben ser True
if edad >= 18 and edad < 65:
    print("Adulto en edad laboral")

# or → al menos una condición debe ser True
if edad < 12 or edad > 70:
    print("Tarifa reducida")

# not → invierte el valor booleano
logueado = False
if not logueado:
    print("Por favor, inicia sesión")
```

### Condicional en una línea (ternario)

```python
mensaje = "Mayor" if edad >= 18 else "Menor"
print(mensaje)
```

---

## Bucles

### Bucle `for`

```python
# Iterar sobre un rango de números
for i in range(5):           # 0, 1, 2, 3, 4
    print(i)

for i in range(1, 6):        # 1, 2, 3, 4, 5
    print(i)

for i in range(0, 10, 2):    # 0, 2, 4, 6, 8 (saltos de 2)
    print(i)

# Iterar sobre una lista
frutas = ["manzana", "pera", "uva"]
for fruta in frutas:
    print(fruta)

# Iterar con índice usando enumerate()
for indice, fruta in enumerate(frutas):
    print(f"{indice}: {fruta}")
# → 0: manzana
# → 1: pera
# → 2: uva
```

### Bucle `while`

```python
contador = 0
while contador < 5:
    print(contador)
    contador += 1

# Bucle infinito controlado con break
while True:
    respuesta = input("Escribe 'salir' para terminar: ")
    if respuesta == "salir":
        break
    print(f"Dijiste: {respuesta}")
```

### Palabras clave de control

```python
for i in range(10):
    if i == 3:
        continue    # Salta esta iteración y continúa
    if i == 7:
        break       # Sale del bucle completamente
    print(i)
# → 0, 1, 2, 4, 5, 6
```

---

## Entrada del Usuario

```python
# input() siempre devuelve un string
nombre = input("¿Cómo te llamas? ")
print(f"Hola, {nombre}!")

# Convertir a número
edad = int(input("¿Cuántos años tienes? "))
altura = float(input("¿Cuánto mides (en metros)? "))

# Validar la entrada con un bucle
while True:
    try:
        numero = int(input("Introduce un número entero: "))
        break                  # Sale del bucle si la conversión fue exitosa
    except ValueError:
        print("Eso no es un número entero. Inténtalo de nuevo.")

print(f"Número introducido: {numero}")
```

---

## Funciones

```python
# Función básica
def saludar():
    print("¡Hola!")

saludar()   # → ¡Hola!

# Función con parámetros
def saludar_a(nombre):
    print(f"¡Hola, {nombre}!")

saludar_a("Luis")   # → ¡Hola, Luis!

# Función con valor de retorno
def sumar(a, b):
    return a + b

resultado = sumar(3, 5)
print(resultado)   # → 8

# Parámetros con valor por defecto
def presentar(nombre, edad=18):
    print(f"{nombre} tiene {edad} años.")

presentar("Ana")          # → Ana tiene 18 años.
presentar("Pedro", 25)    # → Pedro tiene 25 años.

# Número variable de argumentos (*args)
def suma_total(*numeros):
    return sum(numeros)

print(suma_total(1, 2, 3, 4, 5))   # → 15

# Argumentos con nombre (**kwargs)
def mostrar_info(**datos):
    for clave, valor in datos.items():
        print(f"{clave}: {valor}")

mostrar_info(nombre="Ana", ciudad="Madrid", edad=28)
# → nombre: Ana
# → ciudad: Madrid
# → edad: 28

# Lambda (función anónima de una línea)
doble = lambda x: x * 2
print(doble(7))   # → 14
```

---

## Clases y POO

```python
# Definición de una clase
class Persona:
    # Variable de clase (compartida por todas las instancias)
    especie = "Homo sapiens"

    # Constructor: se ejecuta al crear un objeto
    def __init__(self, nombre, edad):
        # Atributos de instancia
        self.nombre = nombre
        self.edad = edad

    # Método de instancia
    def presentarse(self):
        return f"Soy {self.nombre} y tengo {self.edad} años."

    # Método especial __str__: define qué muestra print()
    def __str__(self):
        return f"Persona({self.nombre}, {self.edad})"


# Crear objetos (instancias)
p1 = Persona("Ana", 28)
p2 = Persona("Luis", 35)

print(p1.presentarse())    # → Soy Ana y tengo 28 años.
print(p2.nombre)           # → Luis
print(Persona.especie)     # → Homo sapiens
print(p1)                  # → Persona(Ana, 28)


# Herencia
class Empleado(Persona):
    def __init__(self, nombre, edad, empresa):
        super().__init__(nombre, edad)   # Llama al constructor del padre
        self.empresa = empresa

    def presentarse(self):               # Sobreescribe el método del padre
        base = super().presentarse()
        return f"{base} Trabajo en {self.empresa}."


e1 = Empleado("Carlos", 30, "TechCorp")
print(e1.presentarse())
# → Soy Carlos y tengo 30 años. Trabajo en TechCorp.
```

---

## Listas

Las listas son **ordenadas**, **mutables** y permiten **duplicados**.

```python
# Crear una lista
frutas = ["manzana", "pera", "uva", "manzana"]
numeros = [1, 2, 3, 4, 5]
mixta = [1, "hola", True, 3.14]       # Puede mezclar tipos
vacia = []

# Acceder a elementos (índice empieza en 0)
print(frutas[0])     # → manzana
print(frutas[-1])    # → manzana (último elemento)

# Slicing [inicio:fin:paso]  (fin no incluido)
print(numeros[1:4])   # → [2, 3, 4]
print(numeros[:3])    # → [1, 2, 3]
print(numeros[::2])   # → [1, 3, 5]
print(numeros[::-1])  # → [5, 4, 3, 2, 1]  (invertir)

# Modificar elementos
frutas[1] = "melón"
print(frutas)   # → ['manzana', 'melón', 'uva', 'manzana']

# Métodos útiles
frutas.append("kiwi")         # Añade al final
frutas.insert(1, "fresa")     # Inserta en posición 1
frutas.remove("uva")          # Elimina la primera ocurrencia
elemento = frutas.pop()       # Elimina y devuelve el último
elemento = frutas.pop(0)      # Elimina y devuelve el de la posición 0
frutas.sort()                 # Ordena (modifica la lista)
frutas.reverse()              # Invierte el orden
copia = frutas.copy()         # Crea una copia independiente
frutas.clear()                # Vacía la lista

# Información
print(len(numeros))           # → 5  (longitud)
print("pera" in frutas)       # → True/False (comprobar si existe)
print(frutas.count("manzana")) # → número de ocurrencias
print(frutas.index("pera"))   # → índice de la primera ocurrencia

# List comprehension (forma compacta de crear listas)
cuadrados = [x**2 for x in range(1, 6)]
print(cuadrados)              # → [1, 4, 9, 16, 25]

pares = [x for x in range(10) if x % 2 == 0]
print(pares)                  # → [0, 2, 4, 6, 8]
```

---

## Tuplas

Las tuplas son **ordenadas**, **inmutables** (no se pueden modificar) y permiten **duplicados**.

```python
# Crear una tupla
coordenadas = (40.4168, -3.7038)
colores = ("rojo", "verde", "azul")
un_elemento = (42,)           # ← La coma es obligatoria para tuplas de un elemento

# Acceder (igual que las listas)
print(coordenadas[0])         # → 40.4168
print(colores[-1])            # → azul

# Desempaquetar
latitud, longitud = coordenadas
print(latitud)                # → 40.4168

# No se puede modificar
# colores[0] = "amarillo"     # → Error: TypeError

# Útiles como claves de diccionario (las listas no pueden serlo)
mapa = {(0, 0): "origen", (1, 2): "punto A"}
```

---

## Diccionarios

Los diccionarios almacenan pares **clave: valor**. Son **mutables** y las claves deben ser únicas.

```python
# Crear un diccionario
persona = {
    "nombre": "Ana",
    "edad": 28,
    "ciudad": "Madrid"
}

# Acceder a valores
print(persona["nombre"])           # → Ana
print(persona.get("edad"))         # → 28
print(persona.get("email", "N/A")) # → N/A (valor por defecto si no existe)

# Modificar y añadir
persona["edad"] = 29               # Modificar
persona["email"] = "ana@mail.com"  # Añadir nueva clave

# Eliminar
del persona["ciudad"]
valor = persona.pop("email")       # Elimina y devuelve el valor

# Recorrer un diccionario
for clave in persona:
    print(clave)

for clave, valor in persona.items():
    print(f"{clave}: {valor}")

# Solo claves o solo valores
print(list(persona.keys()))        # → ['nombre', 'edad']
print(list(persona.values()))      # → ['Ana', 29]

# Comprobar si una clave existe
if "nombre" in persona:
    print("Tiene nombre")

# Diccionario por comprensión
cuadrados = {x: x**2 for x in range(1, 6)}
print(cuadrados)   # → {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

---

## Matrices

Python no tiene un tipo "matriz" nativo, pero se pueden representar como **listas de listas** o usando **NumPy**.

### Lista de listas (sin librerías)

```python
# Crear una matriz 3x3
matriz = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

# Acceder a un elemento [fila][columna]
print(matriz[0][0])   # → 1  (fila 0, columna 0)
print(matriz[1][2])   # → 6  (fila 1, columna 2)

# Recorrer toda la matriz
for fila in matriz:
    for elemento in fila:
        print(elemento, end=" ")
    print()   # Salto de línea al final de cada fila
# → 1 2 3
# → 4 5 6
# → 7 8 9

# Crear una matriz de ceros 3x4 por comprensión
filas, columnas = 3, 4
ceros = [[0] * columnas for _ in range(filas)]
print(ceros)
# → [[0, 0, 0, 0], [0, 0, 0, 0], [0, 0, 0, 0]]
```

### NumPy (librería para cálculo numérico)

```bash
pip install numpy
```

```python
import numpy as np

# Crear matrices
a = np.array([[1, 2, 3],
              [4, 5, 6]])

b = np.array([[7, 8, 9],
              [1, 2, 3]])

# Información
print(a.shape)    # → (2, 3)  filas x columnas
print(a.dtype)    # → int64

# Matrices especiales
np.zeros((3, 3))             # Matriz de ceros
np.ones((2, 4))              # Matriz de unos
np.eye(3)                    # Matriz identidad 3x3
np.random.randint(0, 10, (3, 3))  # Matriz aleatoria de enteros

# Operaciones (elemento a elemento)
print(a + b)
print(a * 2)
print(a ** 2)

# Producto matricial
c = np.array([[1, 0], [0, 1], [1, 1]])
# print(a @ c)     # Producto matricial con @

# Acceso y slicing
print(a[0, 1])    # → 2  (fila 0, columna 1)
print(a[:, 1])    # → [2, 5]  (toda la columna 1)
print(a[0, :])    # → [1, 2, 3]  (toda la fila 0)
```

---

## Imports y pip

### Importar módulos de la librería estándar

```python
import math
print(math.pi)             # → 3.141592...
print(math.sqrt(16))       # → 4.0

import random
print(random.randint(1, 10))     # Entero aleatorio entre 1 y 10
print(random.choice(["a", "b"])) # Elige un elemento aleatorio

import os
print(os.getcwd())         # Directorio de trabajo actual
os.makedirs("nueva_carpeta", exist_ok=True)

import datetime
hoy = datetime.date.today()
print(hoy)                 # → 2025-03-27

import json
datos = {"nombre": "Ana", "edad": 28}
json_str = json.dumps(datos, indent=2)   # dict → JSON string
print(json_str)
recuperado = json.loads(json_str)        # JSON string → dict
```

### Formas de importar

```python
import math                        # Importa el módulo completo
from math import sqrt, pi          # Importa solo lo que necesitas
from math import sqrt as raiz      # Importa con alias
import numpy as np                 # Módulo con alias (convención)
from os import *                   # Importa todo (⚠️ no recomendado)
```

### pip — Gestión de paquetes

```bash
# Instalar un paquete
pip install nombre_paquete
pip install numpy
pip install requests

# Instalar una versión específica
pip install numpy==1.26.0

# Actualizar un paquete
pip install --upgrade numpy

# Desinstalar
pip uninstall nombre_paquete

# Ver paquetes instalados
pip list

# Ver info de un paquete
pip show numpy

# Guardar dependencias del proyecto
pip freeze > requirements.txt

# Instalar desde requirements.txt
pip install -r requirements.txt
```

> 💡 En Linux/macOS puede ser necesario usar `pip3` en lugar de `pip`.

### Paquetes esenciales más usados

| Paquete | Para qué sirve | Instalación |
|---|---|---|
| `requests` | Hacer peticiones HTTP / consumir APIs | `pip install requests` |
| `numpy` | Cálculo numérico y matrices | `pip install numpy` |
| `pandas` | Análisis y manipulación de datos | `pip install pandas` |
| `matplotlib` | Gráficos y visualización | `pip install matplotlib` |
| `flask` | Servidor web ligero | `pip install flask` |
| `django` | Framework web completo | `pip install django` |
| `sqlalchemy` | ORM para bases de datos | `pip install sqlalchemy` |
| `pytest` | Testing | `pip install pytest` |
| `python-dotenv` | Variables de entorno desde `.env` | `pip install python-dotenv` |

---

## Errores Comunes

### Capturar excepciones con try / except

```python
# Estructura básica
try:
    resultado = 10 / 0
except ZeroDivisionError:
    print("No se puede dividir entre cero.")

# Capturar varios tipos de error
try:
    numero = int(input("Introduce un número: "))
    print(10 / numero)
except ValueError:
    print("Eso no es un número.")
except ZeroDivisionError:
    print("No se puede dividir entre cero.")
except Exception as e:
    print(f"Error inesperado: {e}")
finally:
    print("Esto se ejecuta siempre.")   # Con o sin error

# Lanzar un error manualmente
def dividir(a, b):
    if b == 0:
        raise ValueError("El divisor no puede ser cero.")
    return a / b
```

### Errores frecuentes y su causa

| Error | Causa habitual |
|---|---|
| `SyntaxError` | Error de escritura en el código (falta `:`, paréntesis, etc.) |
| `NameError` | Usas una variable que no existe o está mal escrita. |
| `TypeError` | Operación con tipos incompatibles (`"3" + 3`). |
| `ValueError` | El valor no es válido (`int("hola")`). |
| `IndexError` | Accedes a un índice que no existe en una lista. |
| `KeyError` | Accedes a una clave que no existe en un diccionario. |
| `AttributeError` | Usas un método o atributo que no tiene ese objeto. |
| `ZeroDivisionError` | División entre cero. |
| `ImportError` | El módulo no existe o no está instalado. |
| `IndentationError` | Error de sangría (espacios/tabs inconsistentes). |

---

*Guía generada como referencia rápida. Para la documentación oficial completa: [docs.python.org](https://docs.python.org/es/3/)* 🐍
