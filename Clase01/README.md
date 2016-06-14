# Las bases

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

La pregunta es de niños. Afortunadamente, la comunidad de Haskell no se burló
de mi por dicha pregunta, todo lo contrario, me ayudó a comprederla. Y ahora yo haré lo mismo,
pero describiendo la firma de una función escrita en Elm (que es muy similar).


Ok, la función es la siguiente:

```
myAddFunction : Int -> Int -> Int
myAddFunction a b = a + b
```


[elm-page][http://elm-lang.org/]
