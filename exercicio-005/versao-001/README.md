# Exercício: Gerenciando contas bancárias

[Voltar](../../README.md)

# Índice

<!-- TOC -->

- [1. Descrição](#1-descri%C3%A7%C3%A3o)
- [2. Requisitos](#2-requisitos)
- [3. Exemplo de Uso](#3-exemplo-de-uso)

<!-- /TOC -->

## 1. Descrição

Desenvolva uma classe Java chamada **ContaBancaria** para representar uma conta bancária simples. A classe deve conter os seguintes elementos:

1. **Atributos estáticos e privados**:
   - `taxaDeJuros`: define a taxa de juros para todas as contas bancárias.
2. **Métodos estáticos e públicos**:
   - `setTaxaDeJuros(double taxa)`: define a taxa de juros para todas as contas bancárias.
   - `getTaxaDeJuros()`: retorna a taxa de juros atual.
   - `criarComSaldoZerado()`: retorna um novo objeto com saldo zerado.
3. **Atributos não estáticos e privados**:
   - `saldo`: armazena o saldo atual da conta.
4. **Métodos não estáticos e públicos**:
   - `depositar(double valor)`: deposita uma quantia na conta.
   - `sacar(double valor)`: saca uma quantia da conta.
   - `calcularJuros(int meses)`: calcula e retorna o valor dos juros acumulados após um determinado número de meses, usando a taxa de juros definida.

## 2. Requisitos

1. Implemente um construtor que receba o saldo inicial.
2. Implemente verificação para garantir que o saldo não se torne negativo durante saques.

Implemente a classe **ContaBancaria** e um programa principal para testar o funcionamento do sistema de conta bancária.

## 3. Exemplo de Uso

```java
public class Main {
    public static void main(String[] args) {
        ContaBancaria.setTaxaDeJuros(0.05);

        ContaBancaria conta = ContaBancaria.criarComSaldoZerado();

        conta.depositar(1000.0);
        System.out.println("Saldo após depósito: R$ " + conta.getSaldo());

        conta.sacar(500.0);
        System.out.println("Saldo após saque: R$ " + conta.getSaldo());

        double juros = conta.calcularJuros(12);
        System.out.println("Juros acumulados após 1 ano: R$ " + juros);

        System.out.println("Taxa de juros atual: " + ContaBancaria.getTaxaDeJuros());
    }
}
```

[Voltar](../../README.md)
