# Exercício Java: Bandas de k-pop

Este projeto Java visa criar um sistema de gerenciamento de bandas de K-pop, incorporando classes para Membros, Managers e Bandas, com ênfase em funcionalidades que aprimoram o sistema.

[Voltar](../../README.md)

# Índice

<!-- TOC -->

- [1. Descrição](#1-descri%C3%A7%C3%A3o)
- [2. Classes](#2-classes)
  - [2.1. Membro](#21-membro)
    - [2.1.1. Atributos privados](#211-atributos-privados)
    - [2.1.2. Construtores públicos](#212-construtores-p%C3%BAblicos)
    - [2.1.3. Métodos públicos](#213-m%C3%A9todos-p%C3%BAblicos)
  - [2.2. Manager](#22-manager)
    - [2.2.1. Atributos privados](#221-atributos-privados)
    - [2.2.2. Construtores públicos](#222-construtores-p%C3%BAblicos)
    - [2.2.3. Métodos públicos](#223-m%C3%A9todos-p%C3%BAblicos)
  - [2.3. Banda](#23-banda)
    - [2.3.1. Atributos privados](#231-atributos-privados)
    - [2.3.2. Construtores públicos](#232-construtores-p%C3%BAblicos)
    - [2.3.3. Métodos públicos](#233-m%C3%A9todos-p%C3%BAblicos)
- [3. Requisitos](#3-requisitos)
- [4. Funcionalidades](#4-funcionalidades)
- [5. Exemplo de uso](#5-exemplo-de-uso)

<!-- /TOC -->

## 1. Descrição

Este projeto tem como objetivo criar um sistema de gerenciamento de bandas de K-pop em Java, abrangendo as principais entidades presentes no cenário musical. As classes principais incluem representações para Membros, Managers e Bandas, proporcionando uma estrutura coesa para a organização e manipulação de informações relacionadas ao universo do K-pop.

A implementação não se limita apenas à modelagem das classes, mas também prioriza a entrega de um conjunto de funcionalidades que enriquecem e aprimoram o sistema como um todo.

## 2. Classes

### 2.1. Membro

#### 2.1.1. Atributos privados

| Rótulo     | Tipo      |
| :--------- | :-------- |
| nome       | `String`  |
| idade      | `int`     |
| cargo      | `String`  |
| salario    | `float`   |
| contratado | `boolean` |

#### 2.1.2. Construtores públicos

| Rótulo | Parâmetros                                                                             |
| :----- | :------------------------------------------------------------------------------------- |
| Membro | nome: `String`, idade: `int`, cargo: `String`, salario: `float`, contratado: `boolean` |

#### 2.1.3. Métodos públicos

| Rótulo        | Parâmetros            | Retorno   |
| :------------ | :-------------------- | :-------- |
| getNome       |                       | `String`  |
| setNome       | nome: `String`        |           |
| getIdade      |                       | `int`     |
| setIdade      | idade: `int`          |           |
| getCargo      |                       | `String`  |
| setCargo      | cargo: `String`       |           |
| getSalario    |                       | `float`   |
| setSalario    | salario: `float`      |           |
| isContratado  |                       | `boolean` |
| setContratado | contratado: `boolean` |           |

### 2.2. Manager

#### 2.2.1. Atributos privados

| Rótulo            | Tipo     |
| :---------------- | :------- |
| nome              | `String` |
| idade             | `int`    |
| salario           | `float`  |
| anosDeExperiencia | `int`    |

#### 2.2.2. Construtores públicos

| Rótulo  | Parâmetros                                                               |
| :------ | :----------------------------------------------------------------------- |
| Manager | nome: `String`, idade: `int`, salario: `float`, anosDeExperiencia: `int` |

#### 2.2.3. Métodos públicos

| Rótulo               | Parâmetros               | Retorno  |
| :------------------- | :----------------------- | :------- |
| getNome              |                          | `String` |
| setNome              | nome: `String`           |          |
| getIdade             |                          | `int`    |
| setIdade             | idade: `int`             |          |
| getSalario           |                          | `float`  |
| setSalario           | salario: `float`         |          |
| getAnosDeExperiencia |                          | `int`    |
| setAnosDeExperiencia | anosDeExperiencia: `int` |          |

### 2.3. Banda

#### 2.3.1. Atributos privados

| Rótulo             | Tipo           |
| :----------------- | :------------- |
| nome               | `String`       |
| agencia            | `String`       |
| anoDeEstreia       | `int`          |
| managerResponsavel | `Manager`      |
| listaDeMembros     | `List<Membro>` |

#### 2.3.2. Construtores públicos

| Rótulo | Parâmetros                                                                            |
| :----- | :------------------------------------------------------------------------------------ |
| Banda  | nome: `String`, agencia: `String`, anoDeEstreia: `int`, managerResponsavel: `Manager` |

#### 2.3.3. Métodos públicos

| Rótulo                         | Parâmetros                    | Retorno        |
| :----------------------------- | :---------------------------- | :------------- |
| getNome                        |                               | `String`       |
| setNome                        | nome: `String`                |                |
| getAgencia                     |                               | `String`       |
| setAgencia                     | agencia: `String`             |                |
| getAnoDeEstreia                |                               | `int`          |
| setAnoDeEstreia                | anoDeEstreia: `int`           |                |
| getManagerResponsavel          |                               | `Manager`      |
| setManagerResponsavel          | managerResponsavel: `Manager` |                |
| getListaDeMembros              |                               | `List<Membro>` |
| adicionarMembro                | membroParaAdicionar: `Membro` |                |
| calcularMediaDeIdadeDosMembros |                               | `float`        |
| exibirTodasAsInformacoes       |                               |                |

## 3. Requisitos

Faça **validações**, garantindo que:

1. A idade dos membros seja maior que zero.
1. A idade do manager seja maior que dezoito.
1. O salário não pode ser negativo para membros e managers.
1. O ano de estreia da banda não pode ser um ano futuro.

> Dica: faça as validações **antes** de atribuir os valores nos atributos!

## 4. Funcionalidades

1. Implemente um método na classe **Banda** para adicionar um membro à lista de membros da banda.
1. Implemente um método na classe **Banda** para calcular a média de idade dos membros da banda.
1. Implemente um método na classe **Banda** para exibir todas as informações da banda, incluindo o nome, agência, ano de estreia, informações do manager e a lista de membros.

## 5. Exemplo de uso

```java
public class Main {
    public static void main(String[] args) {
        Membro membro1 = new Membro("Jimin", 25, "Vocalista", 300000.0F, true);
        Membro membro2 = new Membro("Jungkook", 24, "Maknae", 350000.0F, true);

        Manager manager = new Manager("Bang Si-hyuk", 45, 1500000.0F, 15);

        Banda banda = new Banda("BTS", "Big Hit Entertainment", 2013, manager);
        banda.adicionarMembro(membro1);
        banda.adicionarMembro(membro2);

        System.out.println("Média de idade dos membros: " + banda.calcularMediaDeIdadeDosMembros());
        banda.exibirTodasAsInformacoes();
    }
}
```

[Voltar](../../README.md)
