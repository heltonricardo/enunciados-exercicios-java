# Pacote java.util.function

As interfaces funcionais fornecem tipos de destino para expressões lambda e referências de métodos.

## Interfaces para Objetos

| Interface                 | Método característico | Entrada   | Saída   |
| ------------------------- | --------------------- | --------- | ------- |
| `Consumer<T>`             | `accept`              | T         | void    |
| `BiConsumer<T,U>`         | `accept`              | T, U      | void    |
| `ObjDoubleConsumer<T>`    | `accept`              | T, double | void    |
| `ObjIntConsumer<T>`       | `accept`              | T, int    | void    |
| `ObjLongConsumer<T>`      | `accept`              | T, long   | void    |
| `Supplier<T>`             | `get`                 | -         | T       |
| `BooleanSupplier`         | `getAsBoolean`        | -         | boolean |
| `Function<T,R>`           | `apply`               | T         | R       |
| `BiFunction<T,U,R>`       | `apply`               | T, U      | R       |
| `ToDoubleFunction<T>`     | `applyAsDouble`       | T         | double  |
| `ToDoubleBiFunction<T,U>` | `applyAsDouble`       | T, U      | double  |
| `ToIntFunction<T>`        | `applyAsInt`          | T         | int     |
| `ToIntBiFunction<T,U>`    | `applyAsInt`          | T, U      | int     |
| `ToLongFunction<T>`       | `applyAsLong`         | T         | long    |
| `ToLongBiFunction<T,U>`   | `applyAsLong`         | T, U      | long    |
| `UnaryOperator<T>`        | `apply`               | T         | T       |
| `BinaryOperator<T>`       | `apply`               | T, T      | T       |
| `Predicate<T>`            | `test`                | T         | boolean |
| `BiPredicate<T,U>`        | `test`                | T, U      | boolean |

## Interfaces para tipos primitivos

| Interface              | Método característico | Entrada        | Saída   |
| ---------------------- | --------------------- | -------------- | ------- |
| `DoubleConsumer`       | `accept`              | double         | void    |
| `IntConsumer`          | `accept`              | int            | void    |
| `LongConsumer`         | `accept`              | long           | void    |
| `DoubleSupplier`       | `getAsDouble`         | -              | double  |
| `IntSupplier`          | `getAsInt`            | -              | int     |
| `LongSupplier`         | `getAsLong`           | -              | long    |
| `DoubleFunction<R>`    | `apply`               | double         | R       |
| `IntFunction<R>`       | `apply`               | int            | R       |
| `LongFunction<R>`      | `apply`               | long           | R       |
| `DoubleToIntFunction`  | `applyAsInt`          | double         | int     |
| `DoubleToLongFunction` | `applyAsLong`         | double         | long    |
| `IntToDoubleFunction`  | `applyAsDouble`       | int            | double  |
| `IntToLongFunction`    | `applyAsLong`         | int            | long    |
| `LongToDoubleFunction` | `applyAsDouble`       | long           | double  |
| `LongToIntFunction`    | `applyAsInt`          | long           | int     |
| `DoubleUnaryOperator`  | `applyAsDouble`       | double         | double  |
| `IntUnaryOperator`     | `applyAsInt`          | int            | int     |
| `LongUnaryOperator`    | `applyAsLong`         | long           | long    |
| `DoubleBinaryOperator` | `applyAsDouble`       | double, double | double  |
| `IntBinaryOperator`    | `applyAsInt`          | int, int       | int     |
| `LongBinaryOperator`   | `applyAsLong`         | long, long     | long    |
| `DoublePredicate`      | `test`                | double         | boolean |
| `IntPredicate`         | `test`                | int            | boolean |
| `LongPredicate`        | `test`                | long           | boolean |

Referência: [Documentação oficial do Java](https://docs.oracle.com/javase/8/docs/api/java/util/function/package-summary.html)
