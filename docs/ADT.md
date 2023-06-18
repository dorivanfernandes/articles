# ADT (Algebraic data type)

# O que é?

ADT é uma forma de definir e representar estruturas complexas, organizando informações de forma estruturada e concisa. Os ADTs são divididos em dois tipos:

- **Soma**: representa opções que podem ser escolhidas
- **Produto**: representa a combinação de vários valores

### Exemplo:

Você precisa fazer a representação de veículos, que podem ser motos ou carros. Para qualquer veículo é necessário informar seu tipo e placa. Para carros deve existir uma propriedade de quantidade de portas.

```kotlin
sealed class Vehicle(
    val type: VehicleType,
    val licensePlate: String
) {

    enum class VehicleType { Motorcycle, Car }

    class Car(
        licensePlate: String,
        val doorsQuantity: Int
    ) : Vehicle(VehicleType.Car, licensePlate)

    class Motorcycle(
        licensePlate: String
    ) : Vehicle(VehicleType.Motorcycle, licensePlate)
}
```

Nesse exemplo temos os dois tipos de ADT. A sealed class `Vehicle` é o tipo **Soma**, pois essa estrutura nos permite escolher entre `Car` e `Motorcycle`.  Classes e/ou Data Classes, nesse exemplo,`Car` e `Motorcycle`, são tipo **Produto**, visto que é agregação de propriedades. Os Enums, nesse exemplo `VehicleType`, são considerados um tipo simplificado de ADT.