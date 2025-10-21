# CAT 1
Alejandro Pérez Bueno
Oct 21, 2025

- [Exercise 1](#exercise-1)
- [Exercise 2](#exercise-2)



## Exercise 1

``` mermaid
classDiagram
  class Province {
    Integer code <P>
    String name <U1>
    Integer population
    Float area
  }

  class City {
    Integer code <P>
    String name
    String description [0..1]
  }

  class Base {
    Integer code <P>
    String name <U1>
    String address
    Integer totalSpaces
    Integer availableSpaces
  }

  class Bicycle {
    String code <P>
    String model
    Integer batteryPercentage
    Float consumption
    Float rate
    BicycleStatus status
  }

  class BicycleStatus {
    <<enumeration>>
    AVAILABLE
    IN_USE
    DISCHARGED
    OUT_OF_SERVICE
  }

  City "1" --> "0..*" Province : belongsTo
  Base "1" --> "0..*" City : isLocatedIn
  Bicycle "0..1" --> "0..*" Base : isParkedAt

  note for Bicycle "batteryPercentage must be in [0,100]"
  note for Base "availableSpaces could be derived:\ntotalSpaces - count(bicycles via isParkedAt)"
```

## Exercise 2
