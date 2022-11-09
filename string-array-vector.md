# Práctica 09. std::string std::array std::vector

# Factor de ponderación: 8

### Objetivos
Los objetivos de esta práctica son que el alumnado:
* Sea capaz de resolver problemas sencillos en C++ usando todos los conocimientos adquiridos hasta ahora, 
  y en particular utilizando estructuras de datos básicas, `std::string`, `std::array`, `std::vector`
* Conozca los fundamentos del desarrollo dirigido por tests y las pruebas unitarias
* Conozca la plataforma Exercism y sea capaz de interaccionar con la misma para resolver problemas 

### Rúbrica de evaluacion de esta práctica
Se señalan a continuación los aspectos más relevantes (la lista no es exhaustiva) que se tendrán en cuenta a la hora de evaluar esta práctica.
Se comprobará que el alumnado:
* Conoce los conceptos expuestos en el material de referencia de esta práctica.
* Ha realizado todos los ejercicios propuestos en este enunciado
* Es capaz de escribir programas simples en C++ que resuelvan problemas de complejidad similar a los que se proponen en este documento
* Conoce la plataforma Exercism y es capaz de descargar y realizar problemas sencillos interaccionando con ella.
* Es capaz de escribir un fichero `CMakeLists.txt` para automatizar el proceso de compilación de sus programas con `cmake` y `make`
* Ha automatizado la compilación de sus programas usando un fichero `Makefile` para cada uno de los programas que desarrolle 
* Hace que sus programas se estructuren en torno a diferentes funciones (sean modulares)
* Todos sus programas se estructuran en directorios diferentes para cada "proyecto" haciendo que cada uno de
  ellos contenga un fichero `CMakeLists.txt` con la configuración de despliegue del proyecto.
* Utiliza en todos sus programas comentarios adecuados en el formato requerido por
[Doxygen](https://www.doxygen.nl/index.html)
* Acredita que todas las prácticas realizadas hasta la fecha se encuentran alojadas en repositorios privados de 
[GitHub](https://github.com/).
* Acredita que es capaz de subir programas a la plataforma 
[Jutge](https://jutge.org/)
para su evaluación
* Ha incluido un comentario prólogo en todos los ficheros (`*.cc`, `*.h`) de sus ejercicios
* Que todos los programas que desarrolla, antes de su ejecución imprimen en pantalla un mensaje indicando la 
  finalidad del programa así como la información que precisará del usuario para su correcta ejecución.
* Hace que todos los programas que se presentan para su evaluación cumplan con los estándares definidos en la
[Guía de estilo de Google para C++](https://google.github.io/styleguide/cppguide.html) 
* Utiliza siempre identificadores significativos en su programa (para constantes, variables, etc.) y
  no utiliza nunca identificadores de una única letra, tal vez con la excepción de las variables que utilice para iterar en un bucle.
* Acredita que es capaz de editar ficheros remotos en su VM usando vi
* Ha realizado todos sus ejercicios en la máquina virtual Ubuntu de la asignatura.
* Demuestra que es capaz de ejecutar comandos Linux en su VM


### Desarrollo dirigido por tests
Tal como recoge la
[Wikipedia](https://es.wikipedia.org/wiki/Desarrollo_guiado_por_pruebas),
El desarrollo dirigido por tests (TDD, *Test Driven Development* por sus siglas en inglés) es una práctica de 
ingeniería de software que involucra otras dos técnicas: 
escribir las pruebas primero (Test First Development) y 
[Refactorización](https://es.wikipedia.org/wiki/Refactorizaci%C3%B3n)
(Refactoring) o reestructuración del código.
Para escribir las pruebas generalmente se utilizan las pruebas unitarias (unit test en inglés). 

El TDD se basa en la repetición de un ciclo de desarrollo muy corto que
involucra la repetición de tres pasos:
1. En primer lugar el desarrollador escribe un caso de prueba (test) que falla (a propósito) y que define una mejora deseada (habitualmente una nueva función o método)
2. A continuación se desarrolla el código (de la función) que hace que la prueba pase satisfactoriamente 
3. Finalmente refactoriza el nuevo código hasta obtener un resultado satisfactorio

Esta imagen representa este ciclo repetitivo característico del TDD.

![TDD cycle](https://raw.githubusercontent.com/ULL-ESIT-IB-2021-2022/P11-OOP-GoogleTests/main/red-green-refactor.png "Red-Green-Refactor")

El propósito del desarrollo guiado por pruebas es lograr un código limpio que funcione correctamente.
La idea es que los requisitos sean traducidos a pruebas (tests), y de este modo, cuando las pruebas pasen 
se garantizará que el software cumple con los requisitos que se han establecido.


Las "unidades" de código para las que se realizan tests habitualmente son clases, funciones o grupos ellas. 
Supongamos por ejemplo que se está implementando una función (unidad de código) que calcula la suma de dos números enteros.
Una prueba (test unitario) es un código que valida la corrección de esa función: se podría comprobar que lo
que reciba la función sean realmente dos parámetros, y que esos dos parámetros sean números, y que lo que
devuelva la función sea otro número, y que ese número corresponda realmente con la suma. 
Todas estas podrían ser posibles pruebas unitarias que se realicen sobre la función.
Las pruebas unitarias  se suelen realizar utilizando entornos de pruebas (testing) especializados.

Existen diversas plataformas para el desarrollo de tests unitarios en C++.
Algunas de las de uso más extendido son
[Boost.Test](https://www.boost.org/doc/libs/1_49_0/libs/test/doc/html/index.html),
[CppUnit](https://sourceforge.net/projects/cppunit/),
[Cute](https://cute-test.com/)
[Catch2](https://github.com/catchorg/Catch2)
aunque hay
[muchas otras](https://en.wikipedia.org/wiki/List_of_unit_testing_frameworks#C++)

Es fácil encontrar en la web mucha documentación sobre TDD. 
A modo de ejemplo e introducción se recomienda el estudio de
[Mejorar la calidad del código mediante la prueba unitaria](https://www.mql5.com/es/articles/1579).


### Exercism
[Exercism](https://exercism.io/) 
es una plataforma orientada a aprender a programar o también a mejorar las capacidades de cualquier programadora.
El objetivo de Exercism es servir como medio para aprender a programar en un determinado lenguaje, y para ello se propone
hacerlo mediante la resolución de ejercicios que otros usuarios han planteado. 
Lo que se persigue es que tanto quien resuelve el problema como quien lo planteó aprendan al mismo tiempo. 
Además, la interacción con el resto de la comunidad podrá llevar a debates para determinar cuál sería la mejor solución para un determinado problema.

La plataforma se basa en una una aplicación ejecutable en línea de comandos disponible para diferentes sistemas
operativos (Linux, Mac, Windows).
Usando esa aplicación, un usuario puede descargar una serie de ejercicios de programación disponibles en la
en Exercism y realizar los correspondientes programas hasta que consiga pasar los diferentes tests que se
suministran con cada ejercicio.

La plataforma puede ser usada en "modo práctica", en cuyo caso no existe la opción de mentorización (solicitar
que una experta le ayude con sus ejercicios), pero aún así merece la pena practicar los múltiples ejercicios 
que hallará en la plataforma.

## Primeros pasos en Exercism
Comience por 
[registrarse en Exercism](https://exercism.io/users/sign_up). 
Si lo desea, puede Ud. hacerlo usando la cuenta de GitHub de la que ya dispone.
Una vez disponga de una cuenta, configure lo básico de la misma y elija un "track" (un lenguaje) en el que
desee practicar.
Obviamente se propone que elija el track correspondiente a C++.

Propóngase a continuación resolver el problema
["Hello World"](https://exercism.org/tracks/cpp/exercises/hello-world).
En la página de ese problema (o de cualquier otro) hallará Ud. un enlace que indica 
[Learn more about solving exercises
locally](https://exercism.org/docs/using/solving-exercises/working-locally).
Si sigue ese enlace le llevará a la página *Working Locally* que explica cómo trabajar con la plataforma en su
máquina local.
Desde esa página (*Installing the CLI*) se accede al enlace
[Welcome to the Exercism installation guide!](https://exercism.org/cli-walkthrough)
donde hallará instrucciones sobre cómo instalar `Exercism` en su máquina.
En este documento se propone instalarla en la máquina virtual de la asignatura.
Eligiendo la opción *Linux* y a continuación la opción *Using snap* se le pedirá que ejecute
```
$ sudo snap install exercism
```
Ese comando instalará en primer lugar `snap` y a continuación `exercism`, que es lo que se persigue.
También en esa página se indica que se compruebe que la instalación es correcta con el comando
```
$ exercism version
```
[`snap`](https://blogubuntu.com/que-es-ubuntu-snap) 
es un mecanismo alternativo al ya conocido `apt-get install` para instalar aplicaciones en Ubuntu Linux.
Si quiere Ud. saber más sobre `snap` puede consultar
[esta referencia](https://snapcraft.io/docs/getting-started),
aunque ello no es necesario para el trabajo que se propone realizar con Exercism.

Una vez instalada la aplicación `exercism` el siguiente paso es configurar la interfaz de comandos 
(*Command Line Interface*, CLI) de la aplicación.
Para ello se pide que se ejecute el comando
```
$ exercism configure --token=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```
donde el *token* que figura en el comando anterior se encuentra (es específico de cada usuario) en la 
[página de configuración](https://exercism.io/my/settings) 
de la cuenta de usuario que se ha creado.
Basta copiar de esa página el token y colocarlo en el comando anterior.

El comando anterior, una vez ejecutado indica:
```
You have configured the Exercism command-line client:

Config dir:                       /home/usuario/snap/exercism/5/.config/exercism
Token:         (-t, --token)      xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Workspace:     (-w, --workspace)  /home/usuario/snap/exercism/5/exercism
API Base URL:  (-a, --api)        https://api.exercism.io/v1
```
A continuación se puede elegir un problema para pasar a resolverlo.
Se propone, como ya se ha dicho, elegir el problema "*Hello World*".
En la página de cada problema figura una descripción precisa del mismo y 
en la pestaña *Your iterations* hay un enlace
[Learn more about solving exercises locally](https://exercism.org/docs/using/solving-exercises/working-locally)
en el que figuran instrucciones para:
* Download. Descargar el problema mediante el comando `exercism download --exercise=hello-world --track=cpp`
* Solve. Para resolver el problema se propone usar el editor favorito del usuario. Se recomienda usar vim.
* Submit. El comando (`exercism submit`) para subir a la plataforma la solución que el usuario proponga.

Si se ejecuta el comando para descargar el problema el sistema responde:
```
$ exercism download --exercise=hello-world --track=cpp

Downloaded to
/home/usuario/snap/exercism/5/exercism/cpp/hello-world
```
indicando el directorio donde ha colocado el código necesario para trabajar en ese problema.

Si revisa Ud. los ficheros descargados observará que Exercism utiliza `.cpp` como extensión para los ficheros
con código fuente C++ en lugar de la extensión `.cc` que se usa en *Informática Básica*.
La extensión `.cpp` es muy común para ficheros de código C++.

## Ejecución de los tests para un determinado problema
El siguiente paso consiste en editar el programa (en el caso del problema "Hello World" el fichero a editar es
`hello_world.cpp`).
Edite ese fichero hasta que considere que tiene una versión operativa.
Una vez finalizado su programa, el siguiente paso consiste en pasar (superar) los tests del código.
Cada ejercicio de Exercism va acompañado de una serie de tests que el programa debe superar para ser
considerado válido.

Tal como se explica en la página [Running the Tests](https://exercism.io/tracks/cpp/tests), cada problema va
acompañado de sus tests unitarios y de un fichero `CMakeLists.txt` que se
utiliza para automatizar la compilación de los tests y del propio programa.
Tenga en cuenta que **no** debiera modificar el fichero `CMakeLists.txt`.

Tal como se indica en la página anterior y suponiendo que su ejercicio se llame `bob`, 
debieran existir los ficheros `bob.cpp` y `bob.h` antes de ejecutar los tests. 
Esos ficheros podrían estar vacíos, pero han de existir.
En el caso del ejercicio `hello-world` los ficheros son `hello-world.cpp` y `hello-world.h`

El siguiente paso es compilar el programa y los tests unitarios.
Para ello, colóquese en el directorio del ejercicio (`/home/usuario/snap/exercism/5/exercism/cpp/hello-world`)
y ejecute:
```
$ touch hello-world.{h,cpp}
$ mkdir build
$ cd build
$ cmake -G "Unix Makefiles" ..
$ make
```
El comando [touch](https://ss64.com/bash/touch.html) modifica la fecha del fichero (ficheros) que se le pasen
como argumentos. 
El directorio `build` que se crea servirá para alojar (entre otros ficheros) un programa ejecutable que pasará
los tests a su código.
Exercism utiliza `cmake`, de modo que tendrá Ud. que instalar esa aplicación en su VM si no la tiene instalada.

Al ejecutar `cmake -G "Unix Makefiles" ..` CMake creará un fichero Makefile que le servirá para compilar su
ejercicio.
Al ejecutar `make` en el directorio `build` se compilan los tests que ha de pasar su programa.
Si se producen errores de compilación, tendrá Ud. que solucionarlos en el directorio (padre de `build`) de su
ejercicio.
Una vez que se corrijan los errores, `make` construirá y ejecutará los tests que haya disponibles para el
ejercicio en cuestión.

Normalmente cada problema viene acompañado de un conjunto de tests cuyo código se encuentra en un fichero cuyo
nombre tiene el sufijo `_test` (fichero `hello_world_test.cpp` en el caso del ejercicio "Hello
World").
La estrategia que ha de seguir a la hora de progresar en la mejora de su ejercicio es hacer que su código pase
progresivamente las diferentes pruebas (tests) que figuran en ese fichero.
Para ello basta que "mueva" en el código la línea
```
#if defined(EXERCISM_RUN_ALL_TESTS)
```
para situarla después del siguiente test que quiera probar.
La plataforma de testing que utiliza Exercism es 
[Catch2](https://github.com/catchorg/Catch2)
y los tests en formato Catch2 son fáciles de entender.

Cuando su solución al problema pase todos los tests y esté Ud. satisfecha con la misma, puede remitirla a la
plataforma.
Utilice para ello el comando `exercism submit` que hallará Ud. en la página correspondiente al problema.
Una vez que haya enviado su solución a Exercism recibirá un mensaje similar a este:
```
Your solution has been submitted successfully.
You can complete the exercise and unlock the next core exercise at:

https://exercism.io/my/solutions/xxxx
```
A partir de este punto puede ya ver las soluciones que otras usuarias hayan dado al mismo problema o bien
avanzar con otros problemas de ese mismo "track".


### Material de estudio complementario
Estudie todo lo que se indica en el epígrafe 
[Functions](https://google.github.io/styleguide/cppguide.html#Functions)
de la Guía de Estilo de Google y ponga en práctica todo lo que en ella se propone.
Es normal si encuentra en ese epígrafe algún contenido que aún no ha estudiado: no se preocupe. 
Centre su atención en aquellos aspectos que ya conozca, para consolidarlos.

Estudie del
[tutorial de referencia](https://www.learncpp.com/)
en la asignatura los siguientes apartados:
* [Local variables](https://www.learncpp.com/cpp-tutorial/local-variables/)
* [Introduction to global variables](https://www.learncpp.com/cpp-tutorial/introduction-to-global-variables/)
* [Variable shadowing (name hiding)](https://www.learncpp.com/cpp-tutorial/variable-shadowing-name-hiding/)
* [Scope, duration, and linkage summary](https://www.learncpp.com/cpp-tutorial/scope-duration-and-linkage-summary/)
* [Command line arguments](https://www.learncpp.com/cpp-tutorial/command-line-arguments/)

### Ejercicios
* Al realizar los ejercicios cree dentro de su repositorio de esta práctica un directorio diferente
para cada uno de los ejercicios.
Asigne a cada uno de esos directorios nombres significativos. 
* Automatice la compilación del programa correspondiente a cada ejercicio con un fichero `Makefile`
independiente para cada programa e inclúyalo en el correspondiente directorio.
* Haga que todos los programas tomen su entrada por la línea de comandos y en caso de que se ejecuten sin
  pasarles el número adecuado de parámetros impriman en pantalla un mensaje indicando el modo correcto de
  ejecutar el programa.
* El código de cada uno de los programas deberá organizarse de forma modular, es decir haciendo uso de funciones 
* Cada función deberá realizar una única tarea y hacerlo correctamente 
* El identificador de una función debe reflejar claramente lo que la función hace 

1. Solucione todos los problemas que le sea posible en la plataforma Exercism.
Ello le ayudará a mejorar sus capacidades como programadora.
Para la evaluación de esta práctica se le pedirá que, aparte del problema "Hello World!" y de otros
relacionados en este documento, presente la solución
de un problema adicional de Exercism de los etiquetados como "fáciles" (*Easy*).

1. Escriba un programa `function-example.cc` que incluya una función C++ que realice el cálculo de 
la siguiente función matemática de tres variables:

![Función](functionG.png)

```
Public test cases
Input           Output
3 4 5           -0.349927
4.0 1.0 7.0      0.210819
1 2 3           -0.471405
3 2 10.0         0.8
```

* Reducción: Función que devuelva la suma de todos los elementos de un vector
* Min / Max. Función que calcule el valor mínimo, máximo y la media de todos los elementos de un vector
* String: Función que encripte una cadena de texto pasada por parámetro
* String: Función que dada una frase devuelva otra frase con todas las "palabras" invertidas
* Función que concatene dos vectores y devuelva la concatenación

