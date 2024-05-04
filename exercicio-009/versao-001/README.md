# Exercício Java: Manipulador de string

## 1. Descrição

Você foi designado para criar um programa que manipula strings de várias maneiras. Para isso, você deve seguir as etapas abaixo:

1. Crie a interface **ManipuladorString** que declare um método `String aplicar(String str)` para manipulação de strings. Além disso, anote a interface com `@FunctionalInterface`.

2. Implemente a classe **RemovedorDeEspacosExtras** que implementa a interface **ManipuladorString**. Esta classe deve conter um método para remover espaços em branco no início e no fim de uma string.

3. Implemente a classe **InversorString** que implementa a interface **ManipuladorString**. Esta classe deve conter um método para inverter uma string.

4. No método principal (_main_) do seu programa, crie objetos das classes **RemovedorDeEspacosExtras** e **InversorString** e teste os métodos implementados. Obs.: atribua os objetos criados a uma mesma variável do tipo **ManipuladorString** para aplicar polimorfismo.

5. Na função principal (_main_), faça uma expressão lambda (função anônima) que implementa a interface **ManipuladorString**. Essa expressão deve realizar a substituição de todos os caracteres minúsculos por maiúsculos.

## 2. Exemplo de uso

```java
// Classe principal

String textoOriginal = "    Exemplo de texto para o exercício     ";
System.out.println("Texto original: " + textoOriginal);

String semEspacosExtras = manipulador1.aplicar(textoOriginal);
System.out.println("Texto sem espaços extras: " + semEspacosExtras);

String invertida = manipulador2.aplicar(textoOriginal);
System.out.println("Texto invertido: " + invertida);

String maiusculas = manipulador3.aplicar(textoOriginal);
System.out.println("Texto em maiúsculo: " + maiusculas);
```
