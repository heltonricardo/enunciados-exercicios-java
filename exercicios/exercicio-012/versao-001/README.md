# Exercício Java: Manipulação de produtos

[Voltar](../../../README.md)

Vamos criar um programa em Java para trabalhar com uma lista de produtos. Cada produto terá um **nome**, um **preço** e um **desconto** associado. Utilizaremos diferentes tipos de interfaces funcionais para manipular esses produtos.

## Passo 1: Definindo a classe produto

Crie uma classe chamada `Produto` com os seguintes atributos:

- `String` **nome**: para armazenar o nome do produto.
- `Double` **preco**: para armazenar o preço do produto.
- `Double` **desconto**: para armazenar o desconto aplicável ao produto (um valor de 0.0 a 1.0).

> **Dica**: implemente um construtor que receba todos os atributos e o método `toString` para auxiliar no seu teste.

## Passo 2: Implementando as funções anônimas

Agora, vamos criar funções anônimas utilizando diferentes tipos de interfaces funcionais para manipular os produtos. Crie uma classe com método _main_ e faça o que é solicitado:

> **Dica**: [Pacote java.util.function](../../../util/java.util.function.md)

1. **Supplier - _retornarListaDeProdutos_**: Implemente uma função anônima que retorne uma lista com 5 produtos diferentes.

2. **Function - _calcularPrecoFinal_**: Implemente uma função anônima que receba um produto e retorne o preço final após aplicar o desconto.

3. **Predicate - _temFrete_**: Implemente uma função anônima que receba um preço e retorne se ele possui valor de frete. Caso o preço seja menor que R$ 50 retorne verdadeiro, e caso contrário retorne falso.

4. **UnaryOperator - _acrescerFrete_**: Crie uma função anônima que receba um preço e acresça o valor de frete (R$ 9.99) caso se aplique (use o **Predicate** implementado anteriormente).

5. **UnaryOperator - _acrescerImposto_**: Crie uma função anônima que receba um preço e acresça 4.5% referente ao imposto municipal.

6. **UnaryOperator - _arredondarPreco_**: Crie uma função anônima que receba um preço e arredonde para duas casas decimais.

7. **Consumer - _imprimirProduto_**: Crie uma função anônima que receba um produto e imprima suas informações (nome, preço e desconto).

## Passo 3: Unindo todas as funções

Faça um código que use as funções criadas anteriormente, encadeando-as através dos métodos `andThen` das interfaces **Function** e **UnaryOperator**:

1. Calcule o preço do produto com desconto;
2. Acrescente o valor de frete (caso se aplique);
3. Acrescente o valor de imposto;
4. Arredonde o valor para duas casas decimais;
5. Imprima o nome do produto com seu novo preço;
6. Faça isso para todos os produtos existentes, usando o `forEach` da lista do **Supplier**.

> Veja, a seguir, uma sugestão de como o código deve funcionar.
>
> **`Atenção:`** antes de ver o código abaixo, tente fazer por conta própria, pois este trecho já faz parte da resposta!
>
> <details>
>   <summary>Ver código</summary>
>
> ```java
> retornarListaDeProdutos.get().forEach(produto -> {
>           Double novoPreco = calcularPrecoFinal
>                   .andThen(acrescerFrete)
>                   .andThen(acrescerImposto)
>                   .andThen(arredondarPreco)
>                   .apply(produto);
>           imprimirProduto.accept(produto, novoPreco);
>       }
> );
> ```
>
> </details>

[Voltar](../../../README.md)
