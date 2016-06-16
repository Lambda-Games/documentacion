## Las bases

En esta primera sesión, conocerás lo necesario para escribir código en el lenguaje
de programación Elm.

# ¿Elm?
[Elm][elm-page] es un lenguaje de programación funcional que compila a HTML 5
(HTML, JavaScript y CSS).

# Firma de una función
La *firma de la función*, es uno de los términos más utilizados cuando escribes
código en Elm (o en algún lenguaje fuertemente tipado). Simplemente se refiere
al tipo de la función. Tal vez, este es el primer obstáculo con el que te encuentras
al aprender uno de estos lenguajes. De hecho, mi primera pregunta en el canal IRC
de Haskell fue la siguiente:

```
[camm]: Could you please explain to me what does this mean?
[camm]: myAddFunction :: Integer -> Integer -> Integer
```

La pregunta es para novatos. Afortunadamente, la comunidad de Haskell no se burló
de mi pregunta, todo lo contrario, me ayudó a comprederla. Y ahora yo intentaré hacer
lo mismo, pero describiendo la firma de una función escrita en Elm (que es muy similar).

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
Si por ejemplo, tuvieramos una función `f : Int -> Int` esto indicaría que la función `f`
toma un entero y retorna otro entero.
- `myAddFunction a b` es la definición de la función. Primero escribirmos el nombre de la
función y a continuación una notación para sus dos parámetros (en este caso `a` y `b`).
- `= a + b` lo que está a continuación del símbolo `=` (igual) es la implementación de la función.
En este caso, simplemente indica que sumará los parámetros `a` y `b`.

¿Fácil no? Bueno, estoy omitiendo algunos aspectos importantes, que los trataré más adelante.

[elm-page]: http://elm-lang.org/
