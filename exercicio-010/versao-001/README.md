# Exercício Java: Calculadora funcional

[Voltar](../../README.md)

Você foi designado para criar um programa que manipula strings de várias maneiras. Para isso, você deve seguir as etapas abaixo:

1. Crie a interface **Operacao** que declare um método `Double calcular(Double x, Double y)` para manipulação de strings. Além disso, anote a interface com `@FunctionalInterface`.

2. Implemente a classe **Adicao** que implementa a interface **Operacao**. Esta classe deve conter um método para retornar a soma entre os dois valores.

3. Implemente a classe **Divisao** que implementa a interface **Operacao**. Esta classe deve conter um método para retornar a divisão do primeiro valor pelo segundo.

4. Crie uma classe principal com o método _main_ do seu programa, crie objetos das classes **Adicao** e **Divisao** e teste os métodos implementados. Imprima os retornos das chamadas do método `calcular` ao enviar dois argumentos escolhidos por você.

   > Atribua os objetos criados a uma mesma variável do tipo **Operacao** para aplicar polimorfismo.

5. Na função principal (_main_), faça uma expressão lambda (função anônima) que implementa a interface **Operacao**. Essa expressão deve retornar a exponenciação entre os dois valores, sendo o primeiro a base e o segundo o expoente. Faça uma terceira atribuição, à mesma variável usada até agora, mas agora da lambda criada. Imprima o retorno da chamada do método `calcular` ao enviar dois argumentos escolhidos por você.

6. Altere o tipo da variável criada no método _main_ por uma interface que já vem no Java, especificamente do pacote `java.util.function`. Você deverá encontrar uma interface que se adéque aos tipos usados no exercício - existem múltiplas opções. Essas interfaces estão descritas na [documentação oficial do Java](https://docs.oracle.com/javase/8/docs/api/java/util/function/package-summary.html). Para auxiliar, [neste arquivo](../../util/java.util.function.md), você encontra a versão traduzida.

7. Substitua as atribuições de objetos realizadas no passo **4** por expressões lambda, sem alterar as funcionalidades. A criação do objeto da classe **Adicao** deverá ser a implementação de uma soma e a criação do objeto da classe **Divisao** deverá ser a implementação de uma divisão, sempre mantendo a mesma ordem de uso dos parâmetros mencionados naquele passo.

8. Crie um método na classe principal com a mesma assinatura do método `calcular` da interface (<u>mesmo nome</u>, <u>mesmo tipo de retorno</u> e <u>mesma quantidade, ordem e tipos de parâmetros</u>). Esse método deve retornar a subtração do primeiro parâmetro pelo segundo.

   > O método criado deve ser **estático** pois será referenciado do método _main_, que também é estático.

   > Perceba que neste momento, alguns arquivos do execício (interface e classes que a implementam) não são mais necessários. É opcional excluir esses arquivos neste ponto do exercício.

9. Atribua a **referência do método** criado no passo anterior à variável da _main_. Novamente, imprima o retorno da chamada do método `calcular` ao enviar dois argumentos escolhidos por você.

[Voltar](../../README.md)
