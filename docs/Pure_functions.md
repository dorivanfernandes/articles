# Pure functions

# O que é?

Em programação, função pura é a função que não realiza alterações e nem é afetada por nada fora do seu escopo. Isso garante que dada uma mesma entrada a função sempre retornará a mesma saída sem gerar efeitos colaterais.

### Exemplos

A função `soma`abaixo é um exemplo de função pura, pois sempre que for informado `2`e `2`como entrada o resultado será `4`e essa função não depende e nem altera nada fora do seu escopo.

```kotlin
fun soma(a: Int, b:Int) = a + b

fun main() {
    println(soma(2, 2))
}
```

Já no exemplo abaixo a função `soma` é impura, visto que ela depende da variável `total`, que está fora do seu escopo. Essa função também gera o efeito colateral de alterar o valor da variável `total`

```kotlin
var total = 0
fun soma(a: Int) {
    total += a
}

fun main() {
    (0..5).forEach {
        soma(2)
        println(total)
    }
}
```

# Vantagens

Por não possuir efeitos colaterais, os resultados das funções puras são mais previsíveis, facilitando a criação de testes (principalmente unitários) e facilitando a depuração, caso necessário. São mais seguras para usar em ambientes concorrentes, pois não alteram estado que precisa ser compartilhado entre threads. 

# Desvantagens

O uso de funções puras pode ser limitado, visto que várias partes do desenvolvimento do código são naturalmente impuras, por exemplo, acesso ao banco de dados ou requisições para APIs. Funções puras não podem lançar exceções o que trazer uma abordagem mais complexa para o desenvolvimento na tentativa de tratar os erros sem deixar a função impura.