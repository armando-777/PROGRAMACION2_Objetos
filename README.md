# PRACTICA 1
# Descripcion general de la Practica
Esta practica se centró en la aplicación práctica de los conceptos clave de la programación orientada a objetos (POO): la capacidad de simplificar la complejidad mediante la abstracción, la protección de datos a través del encapsulamiento, la reutilización de código mediante la herencia y la flexibilidad del comportamiento a través del polimorfismo.

Como proyecto principal, se desarrolló una calculadora capaz de realizar operaciones aritméticas elementales, como sumar, restar, multiplicar y dividir. A partir de esta estructura fundamental, se construyó una calculadora de factoriales, heredando las capacidades de la calculadora base y agregando la funcionalidad para calcular el factorial de un número. Además, se modificó la forma en que se mostraba el resultado.

Para obtener una perspectiva más amplia, también se implementaron estas mismas operaciones utilizando un enfoque de programación procedimental. Esto permitió comparar directamente los dos estilos de programación y comprender mejor las ventajas que la programación orientada a objetos ofrece en términos de diseño de software y organización del código."

# Configuracion del entorno y ejecucion del archivo principal
1. Clonar el repositorio:
```python
git clone https://github.com/yefeza/pg2-practica1.git
cd pg2-practica1
```
2. Crear un entorno virtual:
```python
python -m venv env
```
3. Activar el entorno virtual:

* En Windows:
```python
.\env\Scripts\activate
```
* En Linux o Mac:
```python
source env/bin/activate
```
4. Ejecutar el script:
```python
python main.py
```
5. Desactivar el entorno virtual:
```python
deactivate
```
# Descripción y forma de uso de la clase de calculadora estandar
Se ha desarrollado una clase denominada 'Calculadora' diseñada para llevar a cabo las operaciones matemáticas fundamentales: adición, sustracción, multiplicación y división. Cada una de estas operaciones se ha implementado como un método independiente dentro de la clase, que no solo realiza el cálculo, sino que también proporciona una descripción del resultado.

suma(a, b): Efectúa la adición de los valores 'a' y 'b'.

resta(a, b): Realiza la sustracción de 'b' a 'a'.

multiplicacion(a, b): Calcula el producto de 'a' y 'b'.

division(a, b): Obtiene el cociente de 'a' dividido por 'b'.

Para utilizar esta clase, puedes seguir este ejemplo:

```python
from calculadora_poo import Calculadora  
calculadora = Calculadora()

print(calculadora.suma(10, 5))           
print(calculadora.resta(10, 5))          
print(calculadora.multiplicacion(10, 5)) 
print(calculadora.division(10, 5)) 
```
# Principios de POO que Aplica Y como?

La clase 'Calculadora Estándar' ejemplifica los principios fundamentales de la Programación Orientada a Objetos (POO) a través de su diseño:

* Abstracción:
Simplifica el uso de la calculadora al proporcionar métodos claros y concisos, como 'suma()', 'resta()', 'multiplicación()' y 'división()'.
El usuario se enfoca en qué hacer (las operaciones), no en cómo se realizan internamente.
* Encapsulamiento:
Protege la integridad de los datos al agrupar los atributos (como el resultado de una operación) y los métodos dentro de la clase.
El atributo '_resultado', por ejemplo, es inaccesible directamente desde fuera de la clase, y solo se puede acceder a él a través del método '_mostrar()', lo que garantiza que los datos se manipulen de manera controlada.
* Herencia:
Aunque la clase 'Calculadora' en sí misma no demuestra herencia, está diseñada para ser una clase base.
La clase 'Calculadora Factorial' extiende la funcionalidad de 'Calculadora', heredando y reutilizando sus métodos, particularmente 'multiplicación()'.
* Polimorfismo:
Se manifiesta en la forma en que el método '_mostrar()' se comporta de manera diferente en las clases 'Calculadora' y 'Calculadora Factorial'.
En 'Calculadora', '_mostrar()' presenta el resultado de operaciones aritméticas básicas, mientras que en 'Calculadora Factorial', se adapta para mostrar el resultado del cálculo del factorial.
Esto permite utilizar un mismo nombre de método, para mostrar diferentes resultados dependiendo del contexto.

# Descripcion y forma de uso de la clase calculadorafactorial

La clase 'Calculadora Factorial' se construye extendiendo la clase 'Calculadora' existente, lo que le permite heredar sus funcionalidades básicas y, al mismo tiempo, agregar la capacidad de calcular el factorial de números enteros.

* Características clave:

* Reutilización de código:
Aprovecha el método 'multiplicar()' heredado de la clase 'Calculadora' para llevar a cabo los cálculos necesarios para el factorial.

* Funcionalidad adicional:
Introduce un nuevo método llamado 'calcular()', que toma un número entero como entrada y devuelve su factorial correspondiente.

* Adaptación de la presentación de resultados:
Modifica el método responsable de mostrar los resultados, personalizándolo para que refleje la operación de factorial.

* Ejemplo de uso:

```python

from calculadora_factoriall import CalculadoraFactorial
factorial_calculadora = CalculadoraFactorial(5)
print(factorial_calculadora.calcular()) 
```

El proceso de cálculo del factorial se implementa mediante un bucle 'while', que realiza multiplicaciones sucesivas desde 1 hasta el número dado. El resultado final se almacena y se presenta con un formato de salida específico.

```python

while cont <= self.numero:
    factorial = self.multiplicar(factorial, cont)
    cont += 1
self._resultado = factorial
return self._mostrar_opecaiones()

def _mostrar_opecaiones(self):
    return f"{self.operacion}: {self.numero} = {self._resultado}"
```

En resumen, la clase 'Calculadora Factorial' demuestra cómo la herencia permite extender y adaptar funcionalidades existentes para crear herramientas más especializadas."

# Principios de POO que Aplica Y como?

La clase 'Calculadora Factorial' simplifica la complejidad del cálculo del factorial, permitiendo a los usuarios obtener resultados sin preocuparse por los detalles de implementación. Esto se logra mediante los siguientes principios de la programación orientada a objetos (POO):

* Abstracción:
El usuario interactúa únicamente con el método 'calcular()', que oculta la lógica interna de cómo se multiplican los números para obtener el factorial.
Esto permite una experiencia de usuario simplificada, centrada en obtener el resultado deseado.

* Encapsulamiento:
Los detalles del cálculo se protegen dentro de la clase, con el resultado almacenado en el atributo privado '_resultado'.
El acceso a este resultado se controla a través del método '_mostrar_opecaiones()', garantizando la integridad de los datos.

* Herencia:
Al derivar de la clase 'Calculadora', 'Calculadora Factorial' aprovecha métodos existentes como 'multiplicar()', evitando la duplicación de código.
Esto promueve la reutilización y la modularidad del código.

* Polimorfismo:
La clase 'Calculadora Factorial' redefine el comportamiento del método '_mostrar_opecaiones()', adaptándolo para mostrar el resultado del factorial.
Aunque comparte nombre con el método de la clase base, su funcionalidad se ajusta al contexto específico del cálculo del factorial.

En resumen, 'Calculadora Factorial' demuestra cómo la POO facilita la creación de código claro, reutilizable y adaptable, al tiempo que oculta la complejidad innecesaria para el usuario."

# Diferencia entre la implementacion de procedimiento y orientada a objetos

* Programación Procedimental: 

En el paradigma de la programación procedimental, el desarrollo de software se estructura como una serie de pasos o procedimientos, representados por funciones, que se ejecutan secuencialmente para completar una tarea. El flujo del programa se orquesta mediante llamadas a estas funciones, y los datos se manejan como entidades separadas que se transmiten entre ellas.

Si bien este enfoque es adecuado para proyectos simples y scripts cortos, presenta limitaciones significativas en la gestión de la complejidad a medida que los proyectos crecen. La modificación de datos puede generar efectos secundarios difíciles de rastrear, lo que dificulta el mantenimiento del código. Además, la reutilización del código se limita principalmente a la invocación de funciones individuales.

* Ejemplo:

```python
base = 5
altura = 10

def area(b, a):
  return b * a

print(f"Área: {area(base, altura)}")
```
* Programación Orientada a Objetos: 

En contraste, la programación orientada a objetos (POO) aborda la complejidad organizando el código en torno a objetos. Estos objetos son instancias de clases, que actúan como plantillas que definen tanto los datos (atributos) que caracterizan al objeto como las acciones (métodos) que puede realizar. La POO se basa en cuatro principios fundamentales:

* Encapsulamiento: Combina datos y métodos dentro de un objeto, restringiendo el acceso directo a los datos y protegiéndolos de modificaciones externas no deseadas.

* Abstracción: Se centra en las características esenciales de un objeto, ocultando los detalles de implementación internos. Esto permite interactuar con los objetos a un nivel superior, sin necesidad de comprender su funcionamiento interno completo.

* Herencia: Permite crear nuevas clases (subclases) que heredan propiedades y comportamientos de clases existentes (superclases). Esto promueve la reutilización del código y la creación de jerarquías de clases relacionadas.

* Polimorfismo: Permite que objetos de diferentes clases respondan al mismo mensaje (llamada a un método) de maneras específicas para su tipo. Esto agrega flexibilidad y extensibilidad al diseño del software.

* Ejemplo:
```python
class Rectangulo:
  def __init__(self, b, a):
    self.base = b
    self.altura = a

  def area(self):
    return self.base * self.altura

rect = Rectangulo(5, 10)
print(f"Área: {rect.area()}")
```
