# Pacote java.util.function

As interfaces funcionais no pacote `java.util.function` fornecem tipos de destino para expressões lambda e referências de métodos, facilitando uma programação mais concisa e funcional em Java.

---

### Interfaces para Objetos

| Interface                 | Método característico | Entrada     | Saída   |
| ------------------------- | --------------------- | ----------- | ------- |
| `Consumer<T>`             | **accept**            | _T_         | void    |
| `BiConsumer<T,U>`         | **accept**            | _T_, _U_    | void    |
| `ObjDoubleConsumer<T>`    | **accept**            | _T_, double | void    |
| `ObjIntConsumer<T>`       | **accept**            | _T_, int    | void    |
| `ObjLongConsumer<T>`      | **accept**            | _T_, long   | void    |
| `Supplier<T>`             | **get**               | -           | _T_     |
| `BooleanSupplier`         | **getAsBoolean**      | -           | boolean |
| `Function<T,R>`           | **apply**             | _T_         | _R_     |
| `BiFunction<T,U,R>`       | **apply**             | _T_, _U_    | _R_     |
| `ToDoubleFunction<T>`     | **applyAsDouble**     | _T_         | double  |
| `ToDoubleBiFunction<T,U>` | **applyAsDouble**     | _T_, _U_    | double  |
| `ToIntFunction<T>`        | **applyAsInt**        | _T_         | int     |
| `ToIntBiFunction<T,U>`    | **applyAsInt**        | _T_, _U_    | int     |
| `ToLongFunction<T>`       | **applyAsLong**       | _T_         | long    |
| `ToLongBiFunction<T,U>`   | **applyAsLong**       | _T_, _U_    | long    |
| `UnaryOperator<T>`        | **apply**             | _T_         | _T_     |
| `BinaryOperator<T>`       | **apply**             | _T_, _T_    | _T_     |
| `Predicate<T>`            | **test**              | _T_         | boolean |
| `BiPredicate<T,U>`        | **test**              | _T_, _U_    | boolean |

---

### Interfaces para tipos primitivos

| Interface              | Método característico | Entrada        | Saída   |
| ---------------------- | --------------------- | -------------- | ------- |
| `DoubleConsumer`       | **accept**            | double         | void    |
| `IntConsumer`          | **accept**            | int            | void    |
| `LongConsumer`         | **accept**            | long           | void    |
| `DoubleSupplier`       | **getAsDouble**       | -              | double  |
| `IntSupplier`          | **getAsInt**          | -              | int     |
| `LongSupplier`         | **getAsLong**         | -              | long    |
| `DoubleFunction<R>`    | **apply**             | double         | _R_     |
| `IntFunction<R>`       | **apply**             | int            | _R_     |
| `LongFunction<R>`      | **apply**             | long           | _R_     |
| `DoubleToIntFunction`  | **applyAsInt**        | double         | int     |
| `DoubleToLongFunction` | **applyAsLong**       | double         | long    |
| `IntToDoubleFunction`  | **applyAsDouble**     | int            | double  |
| `IntToLongFunction`    | **applyAsLong**       | int            | long    |
| `LongToDoubleFunction` | **applyAsDouble**     | long           | double  |
| `LongToIntFunction`    | **applyAsInt**        | long           | int     |
| `DoubleUnaryOperator`  | **applyAsDouble**     | double         | double  |
| `IntUnaryOperator`     | **applyAsInt**        | int            | int     |
| `LongUnaryOperator`    | **applyAsLong**       | long           | long    |
| `DoubleBinaryOperator` | **applyAsDouble**     | double, double | double  |
| `IntBinaryOperator`    | **applyAsInt**        | int, int       | int     |
| `LongBinaryOperator`   | **applyAsLong**       | long, long     | long    |
| `DoublePredicate`      | **test**              | double         | boolean |
| `IntPredicate`         | **test**              | int            | boolean |
| `LongPredicate`        | **test**              | long           | boolean |

---

> [!IMPORTANT]
> Os tipos _T_, _U_ e _R_ são conhecidos como **generics** (tipos genéricos) e podem ser usados com qualquer tipo de objeto, incluindo os tipos primitivos encapsulados em suas classes wrapper correspondentes, como `Integer`, `Double`, `Long`, `Float`, `Short`, `Byte`, `Character`, e `Boolean`.

> [!TIP]
>
> ```java
> Consumer<Produto> imprimirNome = produto -> System.out.println("Nome do produto: " + produto.getNome());
>
> BiConsumer<Produto, Integer> diminuirEstoque = (produto, quantidade) -> produto.setEstoque(produto.getEstoque() - quantidade);
>
> ObjDoubleConsumer<Produto> aplicarDesconto = (produto, desconto) -> {
>     double precoComDesconto = produto.getPreco() * (1 - desconto);
>     produto.setPreco(precoComDesconto);
> };
>
> ObjIntConsumer<Produto> adicionarAoCarrinho = (produto, quantidade) -> {
>     CarrinhoItem item = new CarrinhoItem(produto, quantidade);
>     carrinho.adicionarItem(item);
> };
>
> ObjLongConsumer<Produto> registrarVenda = (produto, timestamp) -> {
>     Venda venda = new Venda(produto, new Date(timestamp));
>     registroDeVendas.adicionarVenda(venda);
> };
>
> Supplier<Produto> criarNovoProduto = () -> new Produto("Novo Produto", 100.0, 50);
>
> BooleanSupplier estaVazio = () -> carrinho.getQuantidadeItens() == 0;
>
> Function<Produto, String> extrairNome = produto -> produto.getNome();
>
> BiFunction<Produto, Integer, Double> calcularTotal = (produto, quantidade) -> produto.getPreco() * quantidade;
>
> ToDoubleFunction<Produto> calcularPreco = produto -> produto.getPreco();
>
> ToDoubleBiFunction<Produto, Integer> calcularPrecoTotal = (produto, quantidade) -> produto.getPreco() * quantidade;
>
> ToIntFunction<Produto> extrairQuantidade = produto -> produto.getQuantidade();
>
> ToIntBiFunction<Produto, Integer> calcularQuantidadeTotal = (produto, quantidade) -> produto.getQuantidade() * quantidade;
>
> ToLongFunction<Produto> extrairTimestamp = produto -> produto.getTimestamp();
>
> ToLongBiFunction<Produto, Integer> calcularTimestampTotal = (produto, quantidade) -> produto.getTimestamp() * quantidade;
>
> UnaryOperator<Produto> duplicarProduto = produto -> new Produto(produto.getNome(), produto.getPreco(), produto.getQuantidade() * 2);
>
> BinaryOperator<Integer> somarValores = (a, b) -> a + b;
>
> Predicate<Produto> filtroPreco = produto -> produto.getPreco() < 50.0;
>
> BiPredicate<Produto, Integer> filtroEstoque = (produto, quantidade) -> produto.getEstoque() >= quantidade;
>
> ```

Referência: [Documentação oficial do Java](https://docs.oracle.com/javase/8/docs/api/java/util/function/package-summary.html)
