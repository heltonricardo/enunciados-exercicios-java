# Pacote java.util.function

As interfaces funcionais no pacote `java.util.function` fornecem tipos de destino para expressões lambda e referências de métodos, facilitando uma programação mais concisa e funcional em Java.

---

### Interfaces para objetos

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

> [!IMPORTANT]
> Os tipos _T_, _U_ e _R_ são conhecidos como **generics** (tipos genéricos) e podem ser usados com qualquer tipo de objeto, incluindo os tipos primitivos encapsulados em suas classes wrapper correspondentes, como `Integer`, `Double`, `Long`, `Float`, `Short`, `Byte`, `Character`, e `Boolean`.

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

### Exemplos de interfaces para objetos

```java
// Consumer<T>
Consumer<Produto> imprimirNome = produto -> System.out.println("Nome do produto: " + produto.getNome());

// BiConsumer<T, U>
BiConsumer<Produto, Integer> diminuirEstoque = (produto, quantidade) -> produto.setEstoque(produto.getEstoque() - quantidade);

// ObjDoubleConsumer<T>
ObjDoubleConsumer<Produto> aplicarDesconto = (produto, desconto) -> {
    double precoComDesconto = produto.getPreco() * (1 - desconto);
    produto.setPreco(precoComDesconto);
};

// ObjIntConsumer<T>
ObjIntConsumer<Produto> adicionarAoCarrinho = (produto, quantidade) -> {
    CarrinhoItem item = new CarrinhoItem(produto, quantidade);
    carrinho.adicionarItem(item);
};

// ObjLongConsumer<T>
ObjLongConsumer<Produto> registrarVenda = (produto, timestamp) -> {
    Venda venda = new Venda(produto, new Date(timestamp));
    registroDeVendas.adicionarVenda(venda);
};

// Supplier<T>
Supplier<Produto> criarNovoProduto = () -> new Produto("Novo Produto", 100.0, 50);

// BooleanSupplier
BooleanSupplier estaVazio = () -> carrinho.getQuantidadeItens() == 0;

// Function<T, R>
Function<Produto, String> extrairNome = produto -> produto.getNome();

// BiFunction<T, U, R>
BiFunction<Produto, Integer, Double> calcularTotal = (produto, quantidade) -> produto.getPreco() * quantidade;

// ToDoubleFunction<T>
ToDoubleFunction<Produto> calcularPreco = produto -> produto.getPreco();

// ToDoubleBiFunction<T, U>
ToDoubleBiFunction<Produto, Integer> calcularPrecoTotal = (produto, quantidade) -> produto.getPreco() * quantidade;

// ToIntFunction<T>
ToIntFunction<Produto> extrairQuantidade = produto -> produto.getQuantidade();

// ToIntBiFunction<T, U>
ToIntBiFunction<Produto, Integer> calcularQuantidadeTotal = (produto, quantidade) -> produto.getQuantidade() * quantidade;

// ToLongFunction<T>
ToLongFunction<Produto> extrairTimestamp = produto -> produto.getTimestamp();

// ToLongBiFunction<T, U>
ToLongBiFunction<Produto, Integer> calcularTimestampTotal = (produto, quantidade) -> produto.getTimestamp() * quantidade;

// UnaryOperator<T>
UnaryOperator<Produto> duplicarProduto = produto -> new Produto(produto.getNome(), produto.getPreco(), produto.getQuantidade() * 2);

// BinaryOperator<T>
BinaryOperator<Integer> somarValores = (a, b) -> a + b;

// Predicate<T>
Predicate<Produto> filtroPreco = produto -> produto.getPreco() < 50.0;

// BiPredicate<T, U>
BiPredicate<Produto, Integer> filtroEstoque = (produto, quantidade) -> produto.getEstoque() >= quantidade;
```

---

### Exemplos de interfaces para tipos primitivos

```java
// DoubleConsumer
DoubleConsumer imprimirNumero = numero -> System.out.println("Número: " + numero);

// IntConsumer
IntConsumer imprimirValor = valor -> System.out.println("Valor: " + valor);

// LongConsumer
LongConsumer imprimirTempo = tempo -> System.out.println("Tempo em milissegundos: " + tempo);

// DoubleSupplier
DoubleSupplier obterValorAleatorio = () -> Math.random() * 100;

// IntSupplier
IntSupplier obterId = () -> geradorDeId.getNextId();

// LongSupplier
LongSupplier obterTempoAtual = () -> System.currentTimeMillis();

// DoubleFunction<R>
DoubleFunction<String> formatarNumero = numero -> String.format("%.2f", numero);

// IntFunction<R>
IntFunction<String> converterInteiroParaString = valor -> Integer.toString(valor);

// LongFunction<R>
LongFunction<LocalDateTime> timestampParaDateTime = tempo -> LocalDateTime.ofInstant(Instant.ofEpochMilli(tempo), ZoneId.systemDefault());

// DoubleToIntFunction
DoubleToIntFunction arredondarParaInteiro = valor -> (int) Math.round(valor);

// DoubleToLongFunction
DoubleToLongFunction converterParaMillis = valor -> (long) (valor * 1000);

// IntToDoubleFunction
IntToDoubleFunction converterInteiroParaDouble = valor -> (double) valor;

// IntToLongFunction
IntToLongFunction converterInteiroParaLong = valor -> (long) valor;

// LongToDoubleFunction
LongToDoubleFunction converterLongParaDouble = valor -> (double) valor;

// LongToIntFunction
LongToIntFunction converterLongParaInt = valor -> (int) valor;

// DoubleUnaryOperator
DoubleUnaryOperator dobrarNumero = numero -> numero * 2;

// IntUnaryOperator
IntUnaryOperator triplicarValor = valor -> valor * 3;

// LongUnaryOperator
LongUnaryOperator aumentarTempo = tempo -> tempo + 1000;

// DoubleBinaryOperator
DoubleBinaryOperator somarNumeros = (a, b) -> a + b;

// IntBinaryOperator
IntBinaryOperator multiplicarValores = (a, b) -> a * b;

// LongBinaryOperator
LongBinaryOperator calcularDiferenca = (inicio, fim) -> fim - inicio;

// DoublePredicate
DoublePredicate validarNumeroPositivo = numero -> numero > 0;

// IntPredicate
IntPredicate validarIdValido = id -> id > 0;

// LongPredicate
LongPredicate validarTempoPassado = tempo -> tempo < System.currentTimeMillis();
```

---

Referência: [Documentação oficial do Java](https://docs.oracle.com/javase/8/docs/api/java/util/function/package-summary.html)
