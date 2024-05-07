# Exercício Java: Informações pessoais

[Voltar](../../../README.md)

# Índice

<!-- TOC -->

- [1. Descrição](#1-descri%C3%A7%C3%A3o)
- [2. Requisitos](#2-requisitos)
- [3. Exemplo de Uso](#3-exemplo-de-uso)

<!-- /TOC -->

## 1. Descrição

Desenvolva uma classe **Pessoa** para gerenciar informações pessoais básicas de uma pessoa. A classe deve conter atributos para armazenar:

- **Nome** (`String`)
- **Idade** (`int`)
- **Altura** (`float`)
- **Salário** (`double`)
- **Estudante** (`boolean`)

## 2. Requisitos

1. Todos os atributos devem ser privados.
2. Todos os atributos devem ter métodos públicos para acessá-los (_getters_) e modificá-los (_setters_).

## 3. Exemplo de Uso

```java
public class Main {
    public static void main(String[] args) {
        Pessoa pessoa = new Pessoa();

        pessoa.setNome("João");
        pessoa.setIdade(25);
        pessoa.setAltura(1.75f);
        pessoa.setSalario(3000.50);
        pessoa.setEstudante(true);

        System.out.println("Nome: " + pessoa.getNome());
        System.out.println("Idade: " + pessoa.getIdade());
        System.out.println("Altura: " + pessoa.getAltura());
        System.out.println("Salário: " + pessoa.getSalario());
        System.out.println("Estudante: " + pessoa.isEstudante());
    }
}
```

[Voltar](../../../README.md)
