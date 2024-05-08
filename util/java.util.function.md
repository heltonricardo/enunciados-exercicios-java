# Pacote java.util.function

As interfaces funcionais fornecem tipos de destino para expressões lambda e referências de métodos.

| Interface               | Método característico | Descrição                                                                                                         |
| ----------------------- | --------------------- | ----------------------------------------------------------------------------------------------------------------- |
| BiConsumer<T,U>         | accept                | Representa uma operação que aceita dois argumentos de entrada e não retorna resultado.                            |
| BiFunction<T,U,R>       | apply                 | Representa uma função que aceita dois argumentos e produz um resultado.                                           |
| BinaryOperator<T>       | apply                 | Representa uma operação com dois operandos do mesmo tipo, produzindo um resultado do mesmo tipo que os operandos. |
| BiPredicate<T,U>        | test                  | Representa um predicado (função que retorna um booleano) de dois argumentos.                                      |
| BooleanSupplier         | getAsBoolean          | Representa um fornecedor de resultados booleanos.                                                                 |
| Consumer<T>             | accept                | Representa uma operação que aceita um único argumento de entrada e não retorna resultado.                         |
| DoubleBinaryOperator    | applyAsDouble         | Representa uma operação com dois operandos double e produz um resultado double.                                   |
| DoubleConsumer          | accept                | Representa uma operação que aceita um único argumento double e não retorna resultado.                             |
| DoubleFunction<R>       | apply                 | Representa uma função que aceita um argumento double e produz um resultado.                                       |
| DoublePredicate         | test                  | Representa um predicado (função que retorna um booleano) de um argumento double.                                  |
| DoubleSupplier          | getAsDouble           | Representa um fornecedor de resultados double.                                                                    |
| DoubleToIntFunction     | applyAsInt            | Representa uma função que aceita um argumento double e produz um resultado int.                                   |
| DoubleToLongFunction    | applyAsLong           | Representa uma função que aceita um argumento double e produz um resultado long.                                  |
| DoubleUnaryOperator     | applyAsDouble         | Representa uma operação em um único operando double que produz um resultado double.                               |
| Function<T,R>           | apply                 | Representa uma função que aceita um argumento e produz um resultado.                                              |
| IntBinaryOperator       | applyAsInt            | Representa uma operação com dois operandos int e produz um resultado int.                                         |
| IntConsumer             | accept                | Representa uma operação que aceita um único argumento int e não retorna resultado.                                |
| IntFunction<R>          | apply                 | Representa uma função que aceita um argumento int e produz um resultado.                                          |
| IntPredicate            | test                  | Representa um predicado (função que retorna um booleano) de um argumento int.                                     |
| IntSupplier             | getAsInt              | Representa um fornecedor de resultados int.                                                                       |
| IntToDoubleFunction     | applyAsDouble         | Representa uma função que aceita um argumento int e produz um resultado double.                                   |
| IntToLongFunction       | applyAsLong           | Representa uma função que aceita um argumento int e produz um resultado long.                                     |
| IntUnaryOperator        | applyAsInt            | Representa uma operação em um único operando int que produz um resultado int.                                     |
| LongBinaryOperator      | applyAsLong           | Representa uma operação com dois operandos long e produz um resultado long.                                       |
| LongConsumer            | accept                | Representa uma operação que aceita um único argumento long e não retorna resultado.                               |
| LongFunction<R>         | apply                 | Representa uma função que aceita um argumento long e produz um resultado.                                         |
| LongPredicate           | test                  | Representa um predicado (função que retorna um booleano) de um argumento long.                                    |
| LongSupplier            | getAsLong             | Representa um fornecedor de resultados long.                                                                      |
| LongToDoubleFunction    | applyAsDouble         | Representa uma função que aceita um argumento long e produz um resultado double.                                  |
| LongToIntFunction       | applyAsInt            | Representa uma função que aceita um argumento long e produz um resultado int.                                     |
| LongUnaryOperator       | applyAsLong           | Representa uma operação em um único operando long que produz um resultado long.                                   |
| ObjDoubleConsumer<T>    | accept                | Representa uma operação que aceita um argumento do tipo objeto e um argumento double, e não retorna resultado.    |
| ObjIntConsumer<T>       | accept                | Representa uma operação que aceita um argumento do tipo objeto e um argumento int, e não retorna resultado.       |
| ObjLongConsumer<T>      | accept                | Representa uma operação que aceita um argumento do tipo objeto e um argumento long, e não retorna resultado.      |
| Predicate<T>            | test                  | Representa um predicado (função que retorna um booleano) de um argumento.                                         |
| Supplier<T>             | get                   | Representa um fornecedor de resultados.                                                                           |
| ToDoubleBiFunction<T,U> | applyAsDouble         | Representa uma função que aceita dois argumentos e produz um resultado double.                                    |
| ToDoubleFunction<T>     | applyAsDouble         | Representa uma função que produz um resultado double.                                                             |
| ToIntBiFunction<T,U>    | applyAsInt            | Representa uma função que aceita dois argumentos e produz um resultado int.                                       |
| ToIntFunction<T>        | applyAsInt            | Representa uma função que produz um resultado int.                                                                |
| ToLongBiFunction<T,U>   | applyAsLong           | Representa uma função que aceita dois argumentos e produz um resultado long.                                      |
| ToLongFunction<T>       | applyAsLong           | Representa uma função que produz um resultado long.                                                               |
| UnaryOperator<T>        | apply                 | Representa uma operação em um único operando que produz um resultado do mesmo tipo que seu operando.              |

Referência: [Documentação oficial do Java](https://docs.oracle.com/javase/8/docs/api/java/util/function/package-summary.html)
