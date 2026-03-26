# FIRSTS STEPS GUIDE

Bienvenido a tu viaje en el desarrollo de software. Este repositorio ha sido cuidadosamente diseñado para guiarte a través de los fundamentos de la programación, desde la configuración de tu entorno de trabajo hasta la creación de proyectos completos, pasando por el control de versiones con Git.

---

> ⚠️ **Nota Importante**
>
> Para un aprendizaje efectivo: Te recomendamos encarecidamente completar todas las actividades iniciales (hasta los proyectos finales) **sin el uso de herramientas de Inteligencia Artificial**. El objetivo es que desarrolles una comprensión profunda de los conceptos básicos y la capacidad de resolver problemas por ti mismo. La IA es una herramienta fantástica para después, no para saltarse el proceso de aprendizaje.

---

## ÍNDICE

1. [Configuración del Entorno de Desarrollo](#configuración-del-entorno-de-desarrollo)
2. [Control de Versiones con Git](#control-de-versiones-con-git)
3. [Fundamentos de Programación](#fundamentos-de-programación)
4. [Ejercicios por Lenguaje](#ejercicios-por-lenguaje)
5. [Proyectos Finales](#proyectos-finales)
6. [Soluciones](#soluciones-a-los-primeros-ejercicios)
7. [Próximos Pasos](#próximos-pasos)

---

## CONFIGURACIÓN DEL ENTORNO DE DESARROLLO

Un buen entorno de trabajo es la base de un buen programador. Sigue estos pasos para tener todo listo.

### Instalaciones Esenciales

#### Visual Studio Code (VS Code)
Editor de código fuente. Es ligero, gratuito y altamente extensible. Descárgalo desde [code.visualstudio.com](https://code.visualstudio.com).

#### Git
Sistema de control de versiones. Imprescindible para gestionar tu código y colaborar. Descárgalo desde [git-scm.com](https://git-scm.com). Durante la instalación, puedes aceptar todas las opciones por defecto.

#### Node.js *(Opcional pero recomendado)*
Necesario para ejecutar entornos de desarrollo modernos y algunas extensiones como Live Server. Descárgalo desde [nodejs.org](https://nodejs.org) (versión LTS).

### Extensiones Recomendadas para VS Code

Una vez instalado VS Code, accede al panel de extensiones (`Ctrl+Shift+X`) e instala las siguientes:

| Extensión | Propósito |
|---|---|
| Spanish Language Pack | Traduce la interfaz de VS Code al español. |
| Prettier - Code formatter | Formatea automáticamente tu código al guardar, manteniendo un estilo consistente. |
| Live Server | Lanza un servidor local con recarga en vivo para desarrollo web. |
| Better Comments | Colorea y categoriza tus comentarios (`TODO`, `!`, `?`, `*`). |
| Error Lens | Muestra errores y advertencias directamente junto a la línea de código. |
| Postman | Permite probar APIs directamente desde VS Code. |
| vscode-icons | Asigna iconos visuales a los diferentes tipos de archivo. |

> **Configuración recomendada:** Para que Prettier formatee al guardar, presiona `Ctrl+,`, busca **"format on save"** y actívalo. Luego, establece Prettier como formateador por defecto.

---

## CONTROL DE VERSIONES CON GIT

Git te permite guardar "fotos" de tu proyecto en el tiempo, experimentar sin miedo y colaborar con otros. Este es el flujo de trabajo básico que usarás a diario.

### Verificar Instalación

Abre una terminal (en VS Code: `Terminal > Nueva Terminal`) y ejecuta:

```bash
git --version
```

Si ves un número de versión, estás listo. Si no, revisa la instalación.

### Clonar este Repositorio

Para obtener una copia local de este proyecto en tu ordenador:

```bash
git clone https://github.com/ggrauggas/TESTS
```

Si quieres acceder a cada `[URL-DEL-REPOSITORIO]` la dirección se encuentra en el botón **"Code"** de la página del repositorio en GitHub.

### Gestión de Ramas (Branches)

Las ramas son líneas de desarrollo independientes. La rama principal suele llamarse `main` o `master`. Para tus ejercicios, crearás tu propia rama.

**Crear una nueva rama y cambiarte a ella:**

```bash
git checkout -b mi-rama-ejercicios
```

**Cambiar entre ramas existentes:**

```bash
git checkout rama-que-quieres-cambiar
```

### Flujo de Trabajo Diario: Añadir, Confirmar y Subir

**1. Ver el estado de tus cambios:**

```bash
git status
```

Este comando te muestra qué archivos han sido modificados o añadidos.

**2. Añadir cambios al área de preparación (staging area):**

Para añadir un archivo específico:

```bash
git add nombre-del-archivo.py
```

Para añadir todos los archivos modificados:

```bash
git add .
```

**3. Confirmar los cambios con un mensaje:**

```bash
git commit -m "Descripción clara y concisa de lo que has hecho"
```

> Ejemplo: `git commit -m "Añade solución del ejercicio de la clase Persona en Python"`

**4. Subir los cambios al repositorio remoto (GitHub):**

```bash
git push origin mi-rama-ejercicios
```

> Si es la primera vez que subes esta rama, Git puede pedirte que configures la rama upstream con el comando que te sugiere.

---

## FUNDAMENTOS DE LA PROGRAMACIÓN

Antes de escribir una sola línea de código en Python o Java, estos son los conceptos universales que debes dominar. Piensa en ellos como los ladrillos con los que construirás cualquier programa.

### Tipos de Datos

Los datos que maneja un programa pueden ser de diferentes tipos.

| Tipo | Descripción | Ejemplo en Python | Ejemplo en Java |
|---|---|---|---|
| **String** (cadena) | Texto, cualquier secuencia de caracteres. | `nombre = "Ana"` | `String nombre = "Ana";` |
| **Integer** (entero) | Números sin decimales. | `edad = 30` | `int edad = 30;` |
| **Float** (decimal) | Números con punto decimal. | `altura = 1.75` | `double altura = 1.75;` |
| **Boolean** (booleano) | Valor verdadero o falso. | `es_mayor = True` | `boolean esMayor = true;` |

### Estructuras de Control

Permiten dirigir el flujo de ejecución del programa.

#### Condicional `if/else`

Ejecuta un bloque de código solo si se cumple una condición.

```python
# Python
edad = 18
if edad >= 18:
    print("Eres mayor de edad")
else:
    print("Eres menor de edad")
```

```java
// Java
int edad = 18;
if (edad >= 18) {
    System.out.println("Eres mayor de edad");
} else {
    System.out.println("Eres menor de edad");
}
```

#### Bucle `for`

Repite un bloque de código un número determinado de veces.

```python
# Python - Imprime los números del 0 al 4
for i in range(5):
    print(i)
```

```java
// Java - Imprime los números del 0 al 4
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

#### Bucle `while`

Repite un bloque de código mientras se cumpla una condición.

```python
# Python
contador = 0
while contador < 5:
    print(contador)
    contador += 1
```

```java
// Java
int contador = 0;
while (contador < 5) {
    System.out.println(contador);
    contador++;
}
```

### Modularidad: Funciones y Métodos

Las funciones permiten agrupar un bloque de código que realiza una tarea específica, para poder reutilizarlo.

```python
# Python - Definir y llamar una función
def saludar(nombre):
    return f"Hola, {nombre}"

mensaje = saludar("Carlos")
print(mensaje)  # Salida: Hola, Carlos
```

```java
// Java - Definir y llamar un método
public class Utilidades {
    public static String saludar(String nombre) {
        return "Hola, " + nombre;
    }
    
    public static void main(String[] args) {
        String mensaje = saludar("Carlos");
        System.out.println(mensaje);  // Salida: Hola, Carlos
    }
}
```

### Programación Orientada a Objetos (POO)

La POO es un paradigma que organiza el código en "objetos" que contienen datos (**atributos**) y comportamientos (**métodos**).

- **Clase:** Es el molde o plantilla. Define cómo será un objeto.
- **Objeto:** Es una instancia concreta creada a partir de una clase.

```python
# Python - Definición de una clase
class Perro:
    # Constructor: se llama al crear un objeto
    def __init__(self, nombre, raza):
        self.nombre = nombre
        self.raza = raza
    
    # Método (comportamiento)
    def ladrar(self):
        return f"{self.nombre} dice: ¡Guau!"

# Crear objetos (instancias)
mi_perro = Perro("Rex", "Labrador")
otro_perro = Perro("Luna", "Beagle")

print(mi_perro.ladrar())   # Salida: Rex dice: ¡Guau!
print(otro_perro.nombre)   # Salida: Luna
```

```java
// Java - Definición de una clase
public class Perro {
    // Atributos (propiedades)
    private String nombre;
    private String raza;
    
    // Constructor
    public Perro(String nombre, String raza) {
        this.nombre = nombre;
        this.raza = raza;
    }
    
    // Método (comportamiento)
    public String ladrar() {
        return this.nombre + " dice: ¡Guau!";
    }
    
    // Getter para acceder al atributo privado
    public String getNombre() {
        return this.nombre;
    }
    
    public static void main(String[] args) {
        Perro miPerro = new Perro("Rex", "Labrador");
        Perro otroPerro = new Perro("Luna", "Beagle");
        
        System.out.println(miPerro.ladrar());
        System.out.println(otroPerro.getNombre());
    }
}
```

---

## EJERCICIOS POR LENGUAJE

A continuación se detallan los ejercicios que debes realizar para cada tecnología. Se recomienda hacerlos en orden.

### 🐍 PYTHON

Python es ideal para principiantes por su sintaxis clara y legible. Se ejecuta con:

```bash
python nombre_archivo.py
```

| # | Ejercicio | Descripción | Conceptos Clave |
|---|---|---|---|
| 1 | **Hola Mundo** | Imprime el texto `"Hola, mundo!"` en la consola. | `print()` |
| 2 | **Operaciones Matemáticas** | Declara dos variables numéricas y muestra el resultado de su suma, resta, multiplicación y división. | Variables, tipos de datos, operadores aritméticos. |
| 3 | **Entrada de Usuario y Condicional** | Solicita al usuario su edad mediante `input()` y muestra si es mayor de edad (>= 18) o no. | `input()`, conversión de tipos (`int()`), condicional `if/else`. |
| 4 | **Validación con Bucle** | Solicita al usuario que introduzca el número 5. Si introduce otro, sigue pidiéndolo. Al final, muestra `"¡Correcto!"`. | Bucle `while`, condicionales. |
| 5 | **Programación Orientada a Objetos** | Crea una clase `Persona` con atributos `nombre`, `edad`, `peso` y `altura`. Incluye un método `mostrar_informacion()`. Crea dos objetos y muestra su información. | Clases, constructor `__init__`, métodos, `self`. |

### ☕ JAVA

Java es un lenguaje de tipado fuerte y compilado. Necesitarás instalar el **JDK** (Java Development Kit). Para compilar y ejecutar:

```bash
javac NombreArchivo.java   # Compila
java NombreArchivo         # Ejecuta
```

| # | Ejercicio | Descripción | Conceptos Clave |
|---|---|---|---|
| 1 | **Hola Mundo** | Crea una clase con un método `main` que imprima `"Hola, mundo!"`. | Estructura de una clase, método `main`, `System.out.println()`. |
| 2 | **Scanner y Entrada** | Usa la clase `Scanner` para solicitar nombre y edad al usuario, luego imprimirlos. | `java.util.Scanner`, `nextLine()`, `nextInt()`. |
| 3 | **Lógica Condicional** | Pide al usuario su edad y determina si es mayor de edad con `if-else`. | `if-else`, operadores de comparación. |
| 4 | **Programación Orientada a Objetos** | Crea una clase `Persona` con atributos privados, constructor, getters y setters. En el `main`, crea una persona y muestra sus datos. | `private`, `public`, encapsulación, getters/setters. |

### 🌐 HTML y CSS

Estas tecnologías definen la estructura y el estilo de las páginas web. No requieren compilación, solo abrir el archivo `.html` en un navegador.

| # | Ejercicio | Descripción | Conceptos Clave |
|---|---|---|---|
| 1 | **Estructura Básica** | Crea un documento HTML con un título `h1`, un párrafo `p` y una división `div` con texto. | `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`, `h1`, `p`, `div`. |
| 2 | **Formulario** | Añade un formulario con campos para nombre y edad, y un botón de enviar. | `<form>`, `<input type="text">`, `<input type="number">`, `<button>`. |
| 3 | **Estilos CSS** | Aplica estilos: primero en línea (`style`), luego con `<style>` en el `<head>`, y finalmente con un archivo `estilos.css` externo. | `color`, `background-color`, `margin`, `padding`, selectores CSS. |

### 🟨 JAVASCRIPT

JavaScript añade interactividad a las páginas web. Se ejecuta en el navegador.

| # | Ejercicio | Descripción | Conceptos Clave |
|---|---|---|---|
| 1 | **Interactividad Básica** | Crea un botón que al hacer clic muestre una alerta con `"¡Botón clickeado!"`. | Evento `onclick`, función `alert()`. |
| 2 | **Capturar y Mostrar Datos** | Escribe una función que capture los valores del formulario (nombre y edad) y los muestre en un párrafo, sin usar `alert()`. | `document.getElementById()`, `.value`, manipulación del DOM (`.innerText`). |

---

## PROYECTOS FINALES

Estos proyectos integran todos los conocimientos adquiridos. Realízalos después de completar los ejercicios individuales.

### Calculadora Web [HTML, CSS, JAVASCRIPT]

Desarrolla una calculadora funcional que pueda realizar las cuatro operaciones básicas: suma, resta, multiplicación y división.

**Estructura esperada:**

- **HTML:** Una interfaz con dos campos `<input type="number">`, cuatro botones (`+`, `-`, `*`, `/`) y un área para mostrar el resultado.
- **CSS:** Estilos para que sea visualmente agradable: botones grandes, colores diferenciados, centrado en la pantalla.
- **JavaScript:** Lógica para capturar valores, realizar la operación, manejar la división entre cero y mostrar el resultado.

**Ejemplo de código base (función suma):**

```javascript
function sumar() {
    // Obtener los valores de los inputs y convertirlos a números
    let numero1 = parseFloat(document.getElementById('num1').value);
    let numero2 = parseFloat(document.getElementById('num2').value);
    
    // Realizar la suma
    let resultado = numero1 + numero2;
    
    // Mostrar el resultado en el elemento con id="resultado"
    document.getElementById('resultado').innerText = "Resultado: " + resultado;
}
```

### ❌⭕ TRES EN RAYA POR CONSOLA [PYTHON O JAVA]

Implementa el clásico juego de Tres en Raya en modo texto a través de la consola. Puedes elegir **Python** o **Java**.

**Lógica del juego:**

1. **Representar el tablero:** Usa una lista (Python) o un array (Java) de 3×3. Las posiciones vacías se representan con `" "`.

2. **Mostrar el tablero** de forma legible:

    ```
     X | O | X
    ---+---+---
       | O |  
    ---+---+---
     O | X | X
    ```

3. **Turnos:** Alterna entre el jugador `"X"` y el jugador `"O"`.

4. **Entrada del usuario:** Solicita las coordenadas del movimiento (fila y columna, de 0 a 2).

5. **Validaciones:**
   - La casilla elegida debe estar vacía.
   - Las coordenadas deben estar dentro del rango válido.

6. **Verificación del ganador:** Después de cada movimiento, comprueba si hay tres en línea (horizontal, vertical o diagonal). Si hay ganador, anúncialo y termina el juego.

7. **Empate:** Si el tablero se llena sin ganador, anuncia el empate y termina el juego.

---

## SOLUCIONES PRIMEROS EJERCICIOS

> 💡 Intenta resolver los ejercicios por tu cuenta antes de consultar las soluciones.

### Soluciones en Python

#### Ejercicio 1: Hola Mundo

```python
# hola_mundo.py
print("Hola, mundo!")
```

#### Ejercicio 2: Operaciones Matemáticas

```python
# operaciones.py
numero1 = 10
numero2 = 5

suma = numero1 + numero2
resta = numero1 - numero2
multiplicacion = numero1 * numero2
division = numero1 / numero2

print("Suma:", suma)
print("Resta:", resta)
print("Multiplicación:", multiplicacion)
print("División:", division)
```

#### Ejercicio 3: Entrada de Usuario y Condicional

```python
# edad.py
edad_str = input("Por favor, introduce tu edad: ")
edad = int(edad_str)

if edad >= 18:
    print("Eres mayor de edad.")
else:
    print("Eres menor de edad.")
```

#### Ejercicio 4: Validación con Bucle

```python
# validacion_numero.py
numero_correcto = 5
numero_usuario = None

while numero_usuario != numero_correcto:
    numero_usuario_str = input("Introduce el número 5: ")
    numero_usuario = int(numero_usuario_str)
    
    if numero_usuario != numero_correcto:
        print("Incorrecto. Inténtalo de nuevo.")

print("¡Correcto!")
```

#### Ejercicio 5: Programación Orientada a Objetos (Clase Persona)

```python
# persona.py
class Persona:
    def __init__(self, nombre, edad, peso, altura):
        self.nombre = nombre
        self.edad = edad
        self.peso = peso      # en kilogramos
        self.altura = altura  # en metros
    
    def mostrar_informacion(self):
        print("--- Información de la persona ---")
        print(f"Nombre: {self.nombre}")
        print(f"Edad: {self.edad} años")
        print(f"Peso: {self.peso} kg")
        print(f"Altura: {self.altura} m")
        print("---------------------------------")

# Crear objetos y mostrar su información
persona1 = Persona("Ana García", 28, 60.5, 1.65)
persona2 = Persona("Luis Pérez", 35, 82.0, 1.78)

persona1.mostrar_informacion()
persona2.mostrar_informacion()
```

### Soluciones en Java

#### Ejercicio 1: Hola Mundo

```java
// HolaMundo.java
public class HolaMundo {
    public static void main(String[] args) {
        System.out.println("Hola, mundo!");
    }
}
```

#### Ejercicio 2: Scanner y Entrada

```java
// EntradaUsuario.java
import java.util.Scanner;

public class EntradaUsuario {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Introduce tu nombre: ");
        String nombre = scanner.nextLine();
        
        System.out.print("Introduce tu edad: ");
        int edad = scanner.nextInt();
        
        System.out.println("Hola " + nombre + ", tienes " + edad + " años.");
        
        scanner.close();
    }
}
```

#### Ejercicio 3: Lógica Condicional (Mayoría de Edad)

```java
// MayorEdad.java
import java.util.Scanner;

public class MayorEdad {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Introduce tu edad: ");
        int edad = scanner.nextInt();
        
        if (edad >= 18) {
            System.out.println("Eres mayor de edad.");
        } else {
            System.out.println("Eres menor de edad.");
        }
        
        scanner.close();
    }
}
```

#### Ejercicio 4: Programación Orientada a Objetos (Clase Persona con Getter/Setter)

```java
// Persona.java
public class Persona {
    // Atributos privados (encapsulación)
    private String nombre;
    private int edad;
    
    // Constructor
    public Persona(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }
    
    // Getter para nombre
    public String getNombre() {
        return this.nombre;
    }
    
    // Setter para nombre
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }
    
    // Getter para edad
    public int getEdad() {
        return this.edad;
    }
    
    // Setter para edad
    public void setEdad(int edad) {
        if (edad >= 0) {
            this.edad = edad;
        } else {
            System.out.println("Edad no válida");
        }
    }
    
    public void mostrarInformacion() {
        System.out.println("Nombre: " + this.nombre);
        System.out.println("Edad: " + this.edad);
    }
    
    public static void main(String[] args) {
        Persona persona = new Persona("Carlos", 25);
        
        System.out.println("--- Datos iniciales ---");
        persona.mostrarInformacion();
        
        // Usar setters para modificar
        persona.setNombre("Carlos López");
        persona.setEdad(26);
        
        System.out.println("\n--- Datos modificados ---");
        persona.mostrarInformacion();
    }
}
```

### Soluciones en HTML, CSS y JavaScript

#### Ejercicios 1 y 2: Estructura, Formulario e Interactividad

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Primera Página Interactiva</title>
    
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f5f5f5;
        }
        h1 { color: #333; text-align: center; }
        .formulario-container {
            background-color: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            margin-bottom: 20px;
        }
        .campo { margin-bottom: 15px; }
        label { display: block; margin-bottom: 5px; font-weight: bold; }
        input[type="text"], input[type="number"] {
            width: 100%;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
            box-sizing: border-box;
        }
        button {
            background-color: #007bff;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            margin-right: 10px;
        }
        button:hover { background-color: #0056b3; }
        .resultado {
            background-color: #e9ecef;
            padding: 15px;
            border-radius: 4px;
            margin-top: 15px;
        }
    </style>
</head>
<body>
    <h1>Formulario de Usuario</h1>
    
    <div class="formulario-container">
        <div class="campo">
            <label for="nombre">Nombre:</label>
            <input type="text" id="nombre" placeholder="Escribe tu nombre">
        </div>
        <div class="campo">
            <label for="edad">Edad:</label>
            <input type="number" id="edad" placeholder="Escribe tu edad">
        </div>
        <button onclick="mostrarDatos()">Mostrar Datos</button>
        <button onclick="mostrarAlerta()">Mostrar Alerta</button>
        <div class="resultado" id="resultado">Los datos se mostrarán aquí...</div>
    </div>
    
    <div class="formulario-container">
        <h3>Calculadora Simple</h3>
        <div class="campo">
            <label for="num1">Número 1:</label>
            <input type="number" id="num1">
        </div>
        <div class="campo">
            <label for="num2">Número 2:</label>
            <input type="number" id="num2">
        </div>
        <button onclick="operacion('suma')">+</button>
        <button onclick="operacion('resta')">-</button>
        <button onclick="operacion('multiplicacion')">*</button>
        <button onclick="operacion('division')">/</button>
        <div class="resultado" id="resultadoCalculadora">Resultado: </div>
    </div>
    
    <script>
        function mostrarDatos() {
            let nombre = document.getElementById('nombre').value;
            let edad = document.getElementById('edad').value;
            let resultadoDiv = document.getElementById('resultado');
            
            if (nombre && edad) {
                resultadoDiv.innerHTML = `
                    <strong>Datos ingresados:</strong><br>
                    Nombre: ${nombre}<br>
                    Edad: ${edad} años<br>
                    ${edad >= 18 ? 'Es mayor de edad' : 'Es menor de edad'}
                `;
            } else {
                resultadoDiv.innerHTML = 'Por favor, completa todos los campos.';
            }
        }
        
        function mostrarAlerta() {
            alert('¡Botón clickeado! Este es el mensaje de alerta.');
        }
        
        function operacion(tipo) {
            let num1 = parseFloat(document.getElementById('num1').value);
            let num2 = parseFloat(document.getElementById('num2').value);
            let resultado, operador;
            
            if (isNaN(num1) || isNaN(num2)) {
                document.getElementById('resultadoCalculadora').innerHTML =
                    'Resultado: Por favor, introduce ambos números.';
                return;
            }
            
            switch(tipo) {
                case 'suma':         resultado = num1 + num2; operador = '+'; break;
                case 'resta':        resultado = num1 - num2; operador = '-'; break;
                case 'multiplicacion': resultado = num1 * num2; operador = '*'; break;
                case 'division':
                    if (num2 === 0) {
                        document.getElementById('resultadoCalculadora').innerHTML =
                            'Resultado: Error, no se puede dividir entre cero.';
                        return;
                    }
                    resultado = num1 / num2; operador = '/'; break;
                default: return;
            }
            
            document.getElementById('resultadoCalculadora').innerHTML =
                `Resultado: ${num1} ${operador} ${num2} = ${resultado}`;
        }
    </script>
</body>
</html>
```

**Explicación del código:**

- **Estructura HTML:** Dos contenedores principales: formulario de usuario y calculadora simple.
- **Estilos CSS:** Fuente, colores, espaciado, bordes redondeados y sombras. Se usa el selector de clase `.formulario-container` para reutilizar estilos.
- **JavaScript:**
  - `mostrarDatos()` — Obtiene los valores con `getElementById()`, los valida y modifica el DOM con `.innerHTML`.
  - `mostrarAlerta()` — Ejemplo de interacción con `alert()`.
  - `operacion(tipo)` — Lógica de la calculadora con validaciones (campos vacíos, división por cero).

---

## PRÓXIMOS PASOS

Una vez que hayas completado todos los ejercicios y los proyectos finales, estarás listo para explorar temas más avanzados:

-  **Manejo de archivos** — leer y escribir en disco.
-  **Conexión a bases de datos.**
-  **Frameworks web** — Flask/Django (Python), Spring Boot (Java), React (JavaScript).
-  **Pruebas unitarias** (testing).
-  **Despliegue de aplicaciones** (deploy).

---

*¡Felicidades por dar el primer paso en tu carrera como desarrollador!* 
