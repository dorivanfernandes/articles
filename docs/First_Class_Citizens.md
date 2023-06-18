# Functions as first-class citizens

# O que é?

É quando a linguagem de programação permite que funções sejam usadas da mesma forma que outros tipos de dados (String ou Double, por exemplo), ou seja, uma função pode ser atribuída à uma variável ou objetos, passadas como argumentos para outras funções e também podem ser retornadas como resultado de uma função.

### Exemplo:

```kotlin
fun main() {
		// a função que calcula o dobro do valor é atribuída a variável 'dobro'
    val dobro: (Int) -> Int = dobro
    println(dobro(10))
}

fun dobro(a: Int) {
	return a * 2
}
```

Vale salientar que o `first-class citizens` e `high order functions` não são a mesma coisa, visto que as `first-class citizens` é apenas  a característica que permite que funções sejam tratadas como outros tipos e as `high order functions` são apenas funções que recebem ou retornam outras funções. O que podemos perceber é que as `high order functions` não poderiam existir sem as `funções de primeira classe`, visto que sem a possibilidade de tratar funções como variáveis também não seria possível enviar funções como parâmetros e nem receber uma função como retorno. 

Para trazer mais visibilidade histórica o termo `first-class citizens` foi introduzido na programação através da linguagem LISP nos anos 60. Já `high order functions`foi popularizado nos anos 70 através da linguagem ML (Metalanguage), sendo visto como uma extensão dos cidadãos de primeira classe.