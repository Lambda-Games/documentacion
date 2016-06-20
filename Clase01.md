## Introducción a Elm

En esta primera sesión, conocerás lo necesario para escribir código en el lenguaje
de programación Elm.

# ¿Elm?
[Elm][elm-page] es un lenguaje de programación funcional que compila a HTML 5
(HTML, JavaScript y CSS). Fue diseñado por [Evan Czaplicki][evan-czaplicki]

# Instalación
Elm puede ser instalado en cualquier plataforma, solo debes de seguir la [guía de instalación][elm-install]
de elm. La forma más sencilla de hacerlo es utilizando [npm][install-npm]:

```
$ npm install -g elm
```

# Herramientas
Una vez instalado el paquete de elm, tendrás acceso a las siguientes herramientas:

- *elm*
- *elm-package*
- *elm-repl*
- *elm-reactor*
- *elm-make*

# Firma de una función
La *firma de la función*, es un término muy común cuando escribes
código en Elm (o en algún otro lenguaje fuertemente tipado). Simplemente se refiere
al *tipo de la función*. Tal vez, este es el primer obstáculo con el que te encuentras
al aprender uno de estos lenguajes. De hecho, mi primera pregunta en el canal IRC
de Haskell (un lenguaje fuertemente tipado) fue la siguiente:

```
[camm]: Could you please explain to me what does this mean?
[camm]: myAddFunction :: Integer -> Integer -> Integer
```

La pregunta es para novatos. Afortunadamente, la comunidad de Haskell no se burló
de mi pregunta, si no todo lo contrario, me ayudó a comprederla. Y ahora yo intentaré hacer
lo mismo, pero describiendo la firma de una función escrita en Elm (la cual es muy similar).

Describamos los componentes de la siguiente función:

```elm
myAddFunction : Int -> Int -> Int
myAddFunction a b = a + b
```

- `myAddFunction` es el nombre de la función
- `:` (dos puntos) son colocados después del nombre de la función para definir su tipo.
- `Int -> Int -> Int` esta notación indica el tipo de la función. Y lo que indica es que
La función tomará 2 números enteros y retornará otro entero. Describiré más sobre
esta notación en otro capítulo, por ahora contentémonos con esta definición.
Por ejemplo, tuvieramos una función `f` del tipo `Int -> Int` esto indicaría
que la función `f` toma como argumento un entero y retornará como resultado
otro entero.
- `myAddFunction a b` es la definición de la función. En la cual, primero escribirmos
el nombre de la función y a continuación un nombre para sus dos parámetros (en este caso `a` y `b`).
- `= a + b` lo que está a continuación del símbolo `=` (igual) es la implementación de la función.
En este caso, simplemente indica que sumará los parámetros `a` y `b`.

¿Fácil no? Bueno, estoy omitiendo algunos aspectos importantes, que los trataré más adelante.

# Ejercicios


[elm-page]: http://elm-lang.org/
[evan-czaplicki]: https://twitter.com/czaplic
[elm-install]: http://elm-lang.org/install
[install-npm]: http://blog.npmjs.org/post/85484771375/how-to-install-npm
