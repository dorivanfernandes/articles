# Higher Order Functions

## O que é?

Funções de alta ordem (Higher order functions) são funções que podem receber funções como parâmetro e/ou retornar funções como resultado. Esse conceito auxilia na diminuição de códigos repetitivos, abstraindo comportamentos que podem ser aplicados antes e/ou depois da função enviada no parâmetro.

A base para uso desse conceito depende da linguagem fornecer suporte as `funções como cidadãos de primeira classe` (functions as first-class citizens).

## Exemplos


```kotlin
fun main() {
    val persons = listOf(
        Person("Alice", 25),
        Person("Maria", 30),
        Person("Jose", 40),
        Person("Pedro", 22)
    )

    val adults = filterPersons(persons) { person ->
        person.age >= 18
    }
    println("Adults: $adults")

    val under30 = filterPersons(persons) { person ->
        person.age < 30
    }
    println("Under 30: $under30")
}

data class Person(val name: String, val age: Int)

fun filterPersons(
    persons: List<Person>, 
    operation: (Person) -> Boolean
): List<Person> {
    val filteredPersons = mutableListOf<Person>()
    persons.forEach { person ->
        if (operation(person)) {
            filteredPersons.add(person)
        }
    }
    return filteredPersons
}

```

Nesse exemplo temos a função `filterPersons` que recebe como parâmetro uma lista de pessoas (com nome e idade) e também uma função. Essa função recebida no parâmetro será executada determinando se `Person` deverá ser retornada ou não. 

Como `filterPersons` recebe outra função como parâmetro, a lógica para filtragem pode variar de acordo com a necessidade sem precisar escrever várias funções parecidas apenas por pequenas mudanças na regra de filtragem. Toda a lógica de criar uma lista de "filtrados", percorrer todos os itens da lista, chamar a função que filtra e adicionar o que for verdadeiro a lista de "filtrados" só precisa ser escrito uma vez, e o que importa, que é a lógica para filtrar, é recebido no parâmetro como função. Isso mostra o quanto higher order functions reduz a repetição de código aplicando as mesma estrutura para diferentes funções.