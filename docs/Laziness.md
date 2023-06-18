# Laziness

# O que é?

É a possibilidade de adiar a avaliação da expressão até o último momento possível, ou seja, o programa não executa a instrução de forma imediata e só faz a avaliação quando é realmente necessário.

### Exemplo

```kotlin
fun main() {
    val numbers: List<Int> by lazy{
        println("Creating list...")
        sleep(5000) // Simulate a long computation
        (0..10).toList()
    }

    println("Starting")
    println(numbers)
    println("The end!")
}
```

Quando executamos esse exemplo utilizando lazy temos a seguinte sequência de execução: 

1. Impressão do `Starting` 
2. Impressão do `Creating list ...`. 
3. A aplicação fica em espera por 5 segundos 
4. Impressão da lista de números 
5. Impressão do `The end!`

Isso significa que a aplicação **não fez** a execução que preenche os valores na variável numbers logo de início, fazendo a avaliação apenas quando o valor foi necessário. 

```kotlin
fun main() {
    val numbers: List<Int> = createList()

    println("Starting")
    println(numbers)
    println("The end!")
}

fun createList(): List<Int> {
    println("Creating list...")
    sleep(5000) // Simulate a long computation
    return (0..10).toList()
}
```

Já se executarmos esse exemplo que não utiliza lazy temos a seguinte sequência de execução: 

1. Impressão do `Creating list ...` 
2. A aplicação fica em espera por 5 segundos 
3. Impressão do `Starting` 
4. Impressão da lista de números 
5. Impressão do `The end!` 

Isso significa que a aplicação **fez** a execução que preenche os valores na variável numbers logo de início, independente se esse valor será utilizado ou não.

# Vantagens

Já que as instruções são avaliadas apenas quando necessário, isso pode economizar recursos computacionais, principalmente quando a avaliação é complexa e demorada, aumentando o desempenho da aplicação. Lazy também pode ser benéfico quando se trabalha com grandes quantidades de dados ou fluxos de dados infinitos.

# Desvantagens

Utilizar o lazy de forma inadequada pode gerar resultados inesperados e o próprio debug pode ser difícil, visto que não se sabe ao certo quando a expressão é avaliada e nem tem como garantir a execução em alguns casos. Outro detalhe é que o lazy pode aumentar o consumo de memória, pois precisa manter o controle de quais expressões foram avaliadas e quais ainda faltam para avaliar