# Pacote java.util.function

As interfaces funcionais fornecem tipos de destino para expressões lambda e referências de métodos.

| Interface               | Descrição                                                                                                         |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------- |
| BiConsumer<T,U>         | Representa uma operação que aceita dois argumentos de entrada e não retorna resultado.                            |
| BiFunction<T,U,R>       | Representa uma função que aceita dois argumentos e produz um resultado.                                           |
| BinaryOperator<T>       | Representa uma operação com dois operandos do mesmo tipo, produzindo um resultado do mesmo tipo que os operandos. |
| BiPredicate<T,U>        | Representa um predicado (função que retorna um booleano) de dois argumentos.                                      |
| BooleanSupplier         | Representa um fornecedor de resultados booleanos.                                                                 |
| Consumer<T>             | Representa uma operação que aceita um único argumento de entrada e não retorna resultado.                         |
| DoubleBinaryOperator    | Representa uma operação com dois operandos double e produz um resultado double.                                   |
| DoubleConsumer          | Representa uma operação que aceita um único argumento double e não retorna resultado.                             |
| DoubleFunction<R>       | Representa uma função que aceita um argumento double e produz um resultado.                                       |
| DoublePredicate         | Representa um predicado (função que retorna um booleano) de um argumento double.                                  |
| DoubleSupplier          | Representa um fornecedor de resultados double.                                                                    |
| DoubleToIntFunction     | Representa uma função que aceita um argumento double e produz um resultado int.                                   |
| DoubleToLongFunction    | Representa uma função que aceita um argumento double e produz um resultado long.                                  |
| DoubleUnaryOperator     | Representa uma operação em um único operando double que produz um resultado double.                               |
| Function<T,R>           | Representa uma função que aceita um argumento e produz um resultado.                                              |
| IntBinaryOperator       | Representa uma operação com dois operandos int e produz um resultado int.                                         |
| IntConsumer             | Representa uma operação que aceita um único argumento int e não retorna resultado.                                |
| IntFunction<R>          | Representa uma função que aceita um argumento int e produz um resultado.                                          |
| IntPredicate            | Representa um predicado (função que retorna um booleano) de um argumento int.                                     |
| IntSupplier             | Representa um fornecedor de resultados int.                                                                       |
| IntToDoubleFunction     | Representa uma função que aceita um argumento int e produz um resultado double.                                   |
| IntToLongFunction       | Representa uma função que aceita um argumento int e produz um resultado long.                                     |
| IntUnaryOperator        | Representa uma operação em um único operando int que produz um resultado int.                                     |
| LongBinaryOperator      | Representa uma operação com dois operandos long e produz um resultado long.                                       |
| LongConsumer            | Representa uma operação que aceita um único argumento long e não retorna resultado.                               |
| LongFunction<R>         | Representa uma função que aceita um argumento long e produz um resultado.                                         |
| LongPredicate           | Representa um predicado (função que retorna um booleano) de um argumento long.                                    |
| LongSupplier            | Representa um fornecedor de resultados long.                                                                      |
| LongToDoubleFunction    | Representa uma função que aceita um argumento long e produz um resultado double.                                  |
| LongToIntFunction       | Representa uma função que aceita um argumento long e produz um resultado int.                                     |
| LongUnaryOperator       | Representa uma operação em um único operando long que produz um resultado long.                                   |
| ObjDoubleConsumer<T>    | Representa uma operação que aceita um argumento do tipo objeto e um argumento double, e não retorna resultado.    |
| ObjIntConsumer<T>       | Representa uma operação que aceita um argumento do tipo objeto e um argumento int, e não retorna resultado.       |
| ObjLongConsumer<T>      | Representa uma operação que aceita um argumento do tipo objeto e um argumento long, e não retorna resultado.      |
| Predicate<T>            | Representa um predicado (função que retorna um booleano) de um argumento.                                         |
| Supplier<T>             | Representa um fornecedor de resultados.                                                                           |
| ToDoubleBiFunction<T,U> | Representa uma função que aceita dois argumentos e produz um resultado double.                                    |
| ToDoubleFunction<T>     | Representa uma função que produz um resultado double.                                                             |
| ToIntBiFunction<T,U>    | Representa uma função que aceita dois argumentos e produz um resultado int.                                       |
| ToIntFunction<T>        | Representa uma função que produz um resultado int.                                                                |
| ToLongBiFunction<T,U>   | Representa uma função que aceita dois argumentos e produz um resultado long.                                      |
| ToLongFunction<T>       | Representa uma função que produz um resultado long.                                                               |
| UnaryOperator<T>        | Representa uma operação em um único operando que produz um resultado do mesmo tipo que seu operando.              |

Referência: [Documentação oficial do Java](https://docs.oracle.com/javase/8/docs/api/java/util/function/package-summary.html)
