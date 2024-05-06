# Exercício Java: Calculadora funcional

[Voltar](../../README.md)

## 1. Descrição

Você foi designado para criar um programa que manipula strings de várias maneiras. Para isso, você deve seguir as etapas abaixo:

1. Crie a interface **Operacao** que declare um método `Double calcular(Double x, Double y)` para manipulação de strings. Além disso, anote a interface com `@FunctionalInterface`.

2. Implemente a classe **Adicao** que implementa a interface **Operacao**. Esta classe deve conter um método para retornar a soma entre os dois valores.

3. Implemente a classe **Divisao** que implementa a interface **Operacao**. Esta classe deve conter um método para retornar a divisão do primeiro valor pelo segundo.

4. Crie uma classe principal com o método _main_ do seu programa, crie objetos das classes **Adicao** e **Divisao** e teste os métodos implementados. Obs.: atribua os objetos criados a uma mesma variável do tipo **Operacao** para aplicar polimorfismo.

5. Na função principal (_main_), faça uma expressão lambda (função anônima) que implementa a interface **Operacao**. Essa expressão deve retornar a exponenciação entre os dois valores, sendo o primeiro a base e o segundo o expoente. Atribua essa função à mesma variável usada até agora.

6. Altere o tipo da variável criada no método _main_ por uma interface que já vem no Java, especificamente do pacote `java.util.function`. Você deverá encontrar uma interface que se adéque aos tipos usados no exercício - existem múltiplas opções. Essas interfaces estão descritas na [documentação oficial do Java](https://docs.oracle.com/javase/8/docs/api/java/util/function/package-summary.html). Para auxiliar, [neste arquivo](../../util/java.util.function.md), você encontra a versão traduzida.

[Voltar](../../README.md)
