# PyCharm: edición y depuración

[PyCharm](https://www.jetbrains.com/pycharm/) es un entorno de desarrollo
integrado o _IDE_, por sus siglas en inglés, desarollado por la compañía
[JetBrains](https://www.jetbrains.com), autora también del famosísimo IDE
IntelliJ IDEA, para el lenguaje de programación Java.

PyCharm viene en dos versiones, una de pago y otra gratuita. A lo largo del
curso utilizaremos la versión gratuita o _community_. Puedes
[descargarla desde la web](https://www.jetbrains.com/pycharm/download/),
para los sistemas operativos Windows, OSX y Linux.

## Nuevo proyecto

1. Lanza PyCharm y crea un nuevo proyecto. Llámalo `practicas-master-python`.

2. Explora la carpeta creada con PyCharm con el explorador de archivos y
comprueba qué la hace diferente a una carpeta creada por tu cuenta.

3. Usa la terminal para llegar hasta el proyecto de PyCharm y muestra todos sus
elementos con `ls -a`. ¿Qué otras diferencias observas?

Las diferencia principal es la existencia de dos carpetas `venv` y `.idea`.
La primera es el entorno virtual del proyecto (hablaremos más sobre [entornos
virtuales](#) en el futuro). La segunda es la carpeta con las preferencias de
PyCharm. Esta carpeta comienza por un punto por lo que no será visible desde
el explorador de carpetas de Linux o Mac.

## Edición

El editor es una herramienta fundamental para cualquier programador. Si bien
un buen editor no hace al buen programador, desde luego, ¡ayuda! Durante el
curso usaremos PyCharm y descubrirás nuevas funcionalidades conforme sean
necesarias pero **no es obligatorio**. Utiliza el editor con el que te
sientas más cómodo y, si nunca has usado uno, plantéate aprender este como
una experiencia más.

1. Crea un nuevo fichero de Python y llámalo `fizzbuzz`.

2. Pega el siguiente código en el fichero recién creado.

```python
def fizzbuzz(up_to: int):
    output = []
    for number in range(1, up_to + 1):
        representation = []

        if number % 3 == 0:
            representation.append('fizz')

        if number % 5 == 0:
            representation.append('buzz')

        if not representation:
            representation.append(str(number))

        output.append(' '.join(representation))

    print(', '.join(output))


if __name__ == '__main__':
    fizzbuzz(100)
```

3. Observa los mensajes de advertencia del editor. ¿Qué indican? ¿Puedes corregirlos?

4. Renombra la variable `representation` a `representation_tokens`. Mira en
el menú secundario, entrada "_Refactor_".

5. Observa la estructura del programa en la vista "_Structure_".

6. Por imitación, crea una nueva función `is_divisible` que encapsule la
comprobación de divisibilidad en las condiciones de los dos primeros `if`. No
cambies nada aun, sólo crea la función.

7. Haz clic sobre el nombre de la función y observa el icono de la bombilla.
Haz clic sobre este y elige la opción "_Specify return type using annotation_".
Escribe `bool` para el tipo de retorno.

8. Vuelve a hacer clic sobre el nombre de la función y luego en la bombilla
pero ahora selecciona "_Insert documentation string stub_". Documenta la
función. Tienes un ejemplo a continuación:

```python
"""
Comprueba la divisibilidad del primer parámetro entre el segundo.

:param number: el número sobre el que se quiere comprobar la divisibilidad.
:param divisor: el criterio de divisibilidad.
:return: True si el primer parámetro es múltiplo del segundo.
"""
```

9. Observa ahora la estructura del programa en la vista "_Structure_". ¿Cómo ha
cambiado?

10. Utiliza la
[selección múltiple](https://blog.jetbrains.com/pycharm/2014/09/feature-spotlight-multiple-selections-in-pycharm/)
para reemplazar la condición de los dos primeros `if` por sendas llamadas a
`is_divisible`. Observa las ayudas a la edición que muestra PyCharm.

11. Presiona la tecla "comando", en Mac, y situate sobre una de las llamadas
a la función `is_divisible` para que esta se subraye y muestre un globo de
ayuda con información sobre la función. Haz clic mientras el símbolo está en
este estado subrayado para saltar a su definición.

Invierte tiempo en familiarizarte con PyCharm. A continuación encontrarás
algunos recursos de utilidad.

* [PyCharm Blog](https://blog.jetbrains.com/pycharm/)
* [PyCharm Reference Card](https://resources.jetbrains.com/storage/products/pycharm/docs/PyCharm_ReferenceCard.pdf)
* [9 reasons you should be using PyCharm](https://blog.michaelckennedy.net/2015/11/19/9-reasons-you-should-be-using-pycharm/)

## Ejecución

Desde PyCharm puedes lanzar tus _scripts_ creando perfiles de ejecución. Los
perfiles aparecen en un desplegable, en la esquina superior derecha de la
pantalla. Como no has ejecutado nada aun, debería aparecer en su lugar un
botón con el texto "_Add Configuration..._".

1. Haz clic derecho sobre el editor y selecciona "_Run 'fizzbuzz'_". Utiliza el
atajo de teclado la próxima vez.

2. Observa la salida en la consola de resultados. Puedes ejecutar el script
de nuevo haciendo clic en el botón con la flecha verde situado a la izquierda
de la consola de resultados.

3. También puedes ejecutar el script haciendo clic sobre la flecha verde
situada en el margen del editor con los números de línea. Cuando te de a
elegir entre los modos de ejecución, elige "_Run 'fizzbuzz'_".

4. Observa ahora el desplegable con los perfiles de ejecución. Debería
aparecer uno con el nombre del _script_ de Python "_fizzbuzz_".

5. Edita el perfil de ejecución haciendo clic sobre "_Edit configurations..._".
Asegúrate de que el perfil seleccionado a la izquierda es "fizzbuzz" y accede
a la sección "_Execution_". Aquí marca la casilla "_Run with Python
console_" y haz clic en "Ok".

6. Lanza el _script_ de nuevo. Espera un poco hasta que la consola se
inicialice y observa lo que ocurre. Puedes terminar la sesión de consola
haciendo clic sobre el cuadrado rojo que acompaña a la consola Python en su
lado izquierdo.

7. Desmarca la casilla "_Run with Python console_" del perfil de ejecución.

Otros modos de ejecución son:

* [Pasar argumentos al _script_ de Python](https://stackoverflow.com/questions/33102272/pycharm-and-sys-argv-arguments)

    Pruébalo con el siguiente _script_:

    ```python
    import sys

    if __name__ == '__main__':
        print('Estos son los argumentos pasados al script:', sys.argv[1:])
    ```

* [Redirigir la entrada estándar para que lea de un fichero](https://www.jetbrains.com/help/pycharm/run-debug-configuration-python.html#0e408845)

    Pruébalo con el siguiente _script_:

    ```python
    import sys

    if __name__ == '__main__':
        print('Este es el contenido de la entrada estándar:')
        for line in sys.stdin.readlines():
            print(line)
    ```

## Depuración

Uno de los aspectos más importantes del desarrollo es la depuración y el
seguimiento de los programas. El depurador integrado de PyCharm permite una
depuración sencilla y su configuración se basa en los mismos perfiles de
ejecución que creamos anteriormente.

1. Coloca un punto de interrupción haciendo clic en el margen del editor,
justo a la derecha del número de línea. Haz clic derecho sobre el editor y
selecciona "_Debug 'fizzbuzz'_". Espera un poco y verás como el programa se
detiene en esta línea.

2. Observa el panel de depuración. A la izquierda aparece la pila de llamadas
y a la derecha la lista de variables. Expande la categoría "_Special
variables_" para ver un listado de las variables "mágicas" de Python. Estos
son valores con un significado especial.

3. Los controles de la depuración se encuentran a la izquierda y en la parte
superior del panel de depuración. El botón verde de la izquierda del panel,
con forma de rectángulo y flecha, reanudará la ejecución. El programa solo se
detendrá en un punto de interrupción (o _breakpoint_). Al no haber ninguno,
el programa continuará hasta el final. Haz clic en este botón.

4. Vuelve a lanzar el depurador. Puedes hacerlo con el atajo de teclado o
desde el icono del bicho (_bug_) en la esquina superior derecha.

5. En la botonera superior, localiza el icono con la flecha azul hacia abajo
("_Step Into_"), que avanzará la ejecución hasta la siguiente instrucción,
profundizando en la función. Haz clic en este botón.

6. Observa cómo ha cambiado el listado de variables, mostrando ahora el
parámetro de la función.

7. Avanza paso a paso con el botón con la flecha azul en ángulo ("_Step Over_")
hasta alcanzar uno de los condicionales. Observa cómo se actualiza el listado de
variables a cada paso y explora los valores.

8. Evalúa la condición del `if` sin ejecutar la línea con el icono con
aspecto de calculadora ("_Evaluate Expression_"). Selecciona el condicional
del `if`, haz clic sobre el icono y, a continuación, en "_Evaluate_". Cierra
la ventana cuando termines.

9. Para ir a la siguiente instrucción **sin entrar en una función**, haremos
clic en el botón "_Step Over_".

10. A veces conviene tener una expresión en observación. Por ejemplo, sería
conveniente tener en observación `is_divisible(number, 3)` y
`is_divisible(number, 5)`. Para ello, haz clic en el icono con el `+` ("_New
Watch_") y escribe la expresión que quieres evaluar. Repite el proceso, una
vez por expresión.

11. Ejecuta algunas vueltas del bucle y observa cómo se actualizan las
variables conforme avanzas en el programa.

12. Interrumpe la ejecución del programa en cualquier momento, haciendo clic
en el icono del cuadrado rojo ("_Stop_").

Familiarizarte con el depurador es importante porque usarás esta herramienta
constantemente para investigar las causas de los funcionamientos erróneos de
tus programas.