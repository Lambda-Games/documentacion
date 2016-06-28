## Introducción a Elm

En esta primera sesión, conocerás lo necesario para escribir código en el lenguaje
de programación Elm.

# ¿Elm?
[Elm][elm-page] es un lenguaje de programación funcional fuertemente tipado que compila a HTML 5
(HTML, JavaScript y CSS). Fue diseñado por [Evan Czaplicki][evan-czaplicki] y
lanzado por primera vez en el año 2012.

# Instalación
Elm puede ser instalado en cualquier plataforma, solo debes de seguir la [guía de instalación][elm-install]
de elm. La forma más sencilla de hacerlo es utilizando [npm][install-npm]:

```
$ npm install -g elm
```

# Herramientas
Una vez instalado el paquete de elm, tendrás acceso a las siguientes herramientas:

- *elm* - Conjunto de herramientas para trabajar con Elm. Básicamente las que
están descritas a continuación:
- *elm-package* - Gestor de paquetes de Elm.
- *elm-repl* - [Read Eval Print Loop][repl] para Elm.
- *elm-reactor* - Servidor HTTP para explorar un proyecto de Elm.
- *elm-make* - Compila el código de elm en código de HTML5.

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

Antes de continuar con el siguiente tema, cuál sería la firma de las siguientes
funciones:

```elm
> addTwo a = a + 2
> operations a b c d = a + b * c / d
> concat str1 str2 = str1 ++ str2 {-- (++) se utiliza para concatenar dos cadenas de caracteres --}
```

Ahora te mostraré la función `map` que tiene la siguiente firma:
`(a -> b) -> List a -> List b` Intenta adivinar qué indica su firma.
Esta función indica que `map` toma una función del tipo
`a -> b` (es decir, una función que toma un valor `a` y retorna un valor `b`)
, una lista de tipo `a` y retorna una lista de tipo `b`.

¿Fácil no? Bueno, estoy omitiendo algunos aspectos importantes, que los trataré más adelante,
pero no te preocupes no será nada complicado. :)

# Funciones de primera clase
Una función de primera clase es una función que es tratada como un [ciudadano de
primera clase][first-class-citizen], es decir, que una función puede ser tratada
como un valor, lo que implica lo siguiente:
- Una función puede asignarse a un identificador. Por ejemplo, asignar la función
`map` a `myMap`.

```elm
myMap : (a -> b) -> List a -> List b
myMap f list = List.map f list
```
- Una función puede ser pasada como un argumento. Por ejemplo, la función
`addTwo a = a + 2` puede ser pasada como parámetro a la función `myMap` para
que sea aplicada a toda la lista `[1,2,3,4,5]`.
```elm
> myMap addTwo [1,2,3,4,5]
```

- Una función puede ser devuelta por otra función. Por ejemplo, la función
`myMapAddTwo` devolverá una función que recibe una lista del tipo `Int` y
retorna otra lista de `Int` (volveré a mencionar esto cuando describa lo que
es el Curryng).
```elm
myMapAddTwo : List Int -> List Int
myMapAddTwo = myMap addTwo
```

La función es más especializada (a diferencia de `map`), debido al poder de la
inferencia de tipos de Elm.

# Funciones de orden superior
Una función de orden superior es una función que cumple con almenos una de las
siguientes características:

- Toma una o más funciones como argumentos.
- Retorna una función como resultado.

Un ejemplo que describe estas dos características es la función `applyFandG`:

```elm
applyFandG : (a -> a) -> (a -> a) -> a -> a
applyFandG f g x = f (g x)
```

en el ejemplo se puede observar que la función `applyFandG` toma como argumento
dos funciones `f` y `g` y los aplica a un valor `x`.

# Ejercicios


[elm-page]: http://elm-lang.org/
[evan-czaplicki]: https://twitter.com/czaplic
[elm-install]: http://elm-lang.org/install
[install-npm]: http://blog.npmjs.org/post/85484771375/how-to-install-npm
[repl]: https://en.wikipedia.org/wiki/Read-eval-print_loop
[first-class-citizen]: https://en.wikipedia.org/wiki/First-class_citizen
