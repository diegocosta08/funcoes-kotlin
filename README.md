## Exercícios Kotlin — Fundamentos com Listas e Funções

## Exercício 1 — Crie uma função de Ordem Superior que receba dois números inteiros de parâmetro e retorne o resultado da soma.

```kotlin
fun calcular(numero1: Int, numero2: Int, operacao: (Int, Int) -> Int): Int {
    return operacao(numero1, numero2)
}

fun main() {
    val soma = { a: Int, b: Int -> a + b }

    val resultado = calcular(10, 10, soma)

    println("O resultado da soma é: $resultado")
}
```
## Exercício 2 — Crie uma função compacta que receba dois números inteiros de parâmetro e retorne o resultado da multiplicação deles.

```kotlin
infix fun Int.somar(b: Int): Int = this + b

fun main() {
    val resultado = 3 somar 4
    println(resultado)
}
```
## Exercício 3 — Crie uma função calculadora que recebe dois inteiros de parâmetro e um terceiro parâmetro do tipo função. Esta função de parâmetro deve receber dois inteiros de parâmetro e retornar um inteiro.

```kotlin
fun calculadora(x: Int, y: Int, operacao: (Int, Int) -> Int?): Int?{
    return operacao(x, y)
}

fun main() {
    val soma = { x: Int, y: Int -> x + y }
    val subtracao = { x: Int, y: Int -> x - y }
    val multiplicacao = { x: Int, y: Int -> x * y }
    val divisao = { x: Int, y: Int ->
    if (y == 0) null else x / y
}
    
    println(calculadora(10, 10, soma))
    println(calculadora(10, 5, subtracao))
    println(calculadora(10, 10, multiplicacao))
    println(calculadora(10, 5, divisao))
    
}
```
## Exercício 4 — Crie uma lista com os números inteiros de 1 a 99 (Utilizando esta lista crie um filtro que retorna uma lista com os números pares contidos na lista original).

```kotlin
fun main() {
    val numeros = (1..99).toList()
    val numerosPares = numeros.filter { it % 2 == 0 }

    println("Usando filter: $numerosPares")
}
```

## Exercício 5 — Crie uma lista de String com 4 nomes (Utilizando o operador  `map`  concatene a string   `Olá`  antes de cada nome).

```kotlin
fun main() {
    val namesList = listOf("Diego", "Thiago", "Thielly", "Gabriele")
    val helloList = namesList.map { "Olá $it" }

    println(helloList)
}
```

## Exercício 6 — Percorrra a lista modificada usando um `forEach`  e imprima todos seus valores.

```kotlin
fun main() {
    val namesList = listOf("Diego", "Thiago", "Thielly", "Gabriele")
    
    val helloList = namesList.map { 
        "Olá $it"
    }.forEach{
        println(it)
    }
}
```
