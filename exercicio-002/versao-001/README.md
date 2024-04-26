# Projeto Java: Sistema de gerenciamento de times de futebol

Este projeto Java tem como objetivo criar um sistema de gerenciamento de times de futebol, incorporando classes para Jogadores, Técnicos e Times, com ênfase em funcionalidades que aprimoram o sistema.

[Voltar](../../README.md)

# Índice

<!-- TOC -->

- [1. Descrição](#1-descri%C3%A7%C3%A3o)
- [2. Classes](#2-classes)
  - [2.1. Jogador](#21-jogador)
    - [2.1.1. Atributos privados](#211-atributos-privados)
    - [2.1.2. Construtores públicos](#212-construtores-p%C3%BAblicos)
    - [2.1.3. Métodos públicos](#213-m%C3%A9todos-p%C3%BAblicos)
  - [2.2. Tecnico](#22-tecnico)
    - [2.2.1. Atributos privados](#221-atributos-privados)
    - [2.2.2. Construtores públicos](#222-construtores-p%C3%BAblicos)
    - [2.2.3. Métodos públicos](#223-m%C3%A9todos-p%C3%BAblicos)
  - [2.3. Time](#23-time)
    - [2.3.1. Atributos privados](#231-atributos-privados)
    - [2.3.2. Construtores públicos](#232-construtores-p%C3%BAblicos)
    - [2.3.3. Métodos públicos](#233-m%C3%A9todos-p%C3%BAblicos)
- [3. Requisitos](#3-requisitos)
- [4. Funcionalidades](#4-funcionalidades)
- [5. Exemplo de uso](#5-exemplo-de-uso)

<!-- /TOC -->

## 1. Descrição

Este projeto visa criar um sistema de gerenciamento de times de futebol em Java, contemplando as principais entidades presentes em um ambiente esportivo. As classes principais incluem representações para Jogadores, Técnicos e Times, proporcionando uma estrutura coesa para a organização e manipulação de informações relacionadas ao mundo do futebol.

A implementação não se limita à modelagem das classes, mas também prioriza a entrega de um conjunto de funcionalidades que enriquecem e aprimoram o sistema como um todo.

## 2. Classes

### 2.1. Jogador

#### 2.1.1. Atributos privados

| Rótulo     | Tipo      |
| :--------- | :-------- |
| nome       | `String`  |
| idade      | `int`     |
| posicao    | `String`  |
| salario    | `float`   |
| contratado | `boolean` |

#### 2.1.2. Construtores públicos

| Rótulo  | Parâmetros                                                                               |
| :------ | :--------------------------------------------------------------------------------------- |
| Jogador | nome: `String`, idade: `int`, posicao: `String`, salario: `float`, contratado: `boolean` |

#### 2.1.3. Métodos públicos

| Rótulo        | Parâmetros            | Retorno   |
| :------------ | :-------------------- | :-------- |
| getNome       |                       | `String`  |
| setNome       | nome: `String`        |           |
| getIdade      |                       | `int`     |
| setIdade      | idade: `int`          |           |
| getPosicao    |                       | `String`  |
| setPosicao    | posicao: `String`     |           |
| getSalario    |                       | `float`   |
| setSalario    | salario: `float`      |           |
| isContratado  |                       | `boolean` |
| setContratado | contratado: `boolean` |           |

### 2.2. Tecnico

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
| Tecnico | nome: `String`, idade: `int`, salario: `float`, anosDeExperiencia: `int` |

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

### 2.3. Time

#### 2.3.1. Atributos privados

| Rótulo             | Tipo            |
| :----------------- | :-------------- |
| nome               | `String`        |
| cidade             | `String`        |
| anoDeFundacao      | `int`           |
| tecnicoResponsavel | `Tecnico`       |
| listaDeJogadores   | `List<Jogador>` |

#### 2.3.2. Construtores públicos

| Rótulo | Parâmetros                                                                            |
| :----- | :------------------------------------------------------------------------------------ |
| Time   | nome: `String`, cidade: `String`, anoDeFundacao: `int`, tecnicoResponsavel: `Tecnico` |

#### 2.3.3. Métodos públicos

| Rótulo                           | Parâmetros                      | Retorno         |
| :------------------------------- | :------------------------------ | :-------------- |
| getNome                          |                                 | `String`        |
| setNome                          | nome: `String`                  |                 |
| getCidade                        |                                 | `String`        |
| setCidade                        | cidade: `String`                |                 |
| getAnoDeFundacao                 |                                 | `int`           |
| setAnoDeFundacao                 | anoDeFundacao: `int`            |                 |
| getTecnicoResponsavel            |                                 | `Tecnico`       |
| setTecnicoResponsavel            | tecnicoResponsavel: `Tecnico`   |                 |
| getListaDeJogadores              |                                 | `List<Jogador>` |
| adicionarJogador                 | jogadorParaAdicionar: `Jogador` |                 |
| calcularMediaDeIdadeDosJogadores |                                 | `float`         |
| exibirTodasAsInformacoes         |                                 |                 |

## 3. Requisitos

Faça **validações**, garantindo que:

1. A idade dos jogadores seja maior que zero.
1. A idade do técnico seja maior que dezoito.
1. O salário não seja negativo para jogadores e técnicos.
1. O ano de fundação do time não pode ser um ano futuro.

> Dica: faça as validações **antes** de atribuir os valores nos atributos!

## 4. Funcionalidades

1. Implemente um método na classe **Time** para adicionar um jogador à lista de jogadores do time.
1. Implemente um método na classe **Time** para calcular a média de idade dos jogadores do time.
1. Implemente um método na classe **Time** para exibir todas as informações do time, incluindo o nome, cidade, ano de fundação, informações do técnico e a lista de jogadores.

## 5. Exemplo de uso

```java
public class Main {
    public static void main(String[] args) {
        Jogador jogador1 = new Jogador("Neymar", 29, "Atacante", 500000.0F, true);
        Jogador jogador2 = new Jogador("Casemiro", 29, "Meio-campista", 300000.0F, true);

        Tecnico tecnico = new Tecnico("Tite", 60, 1000000.0F, 20);

        Time time = new Time("Seleção Brasileira", "Rio de Janeiro", 1914, tecnico);
        time.adicionarJogador(jogador1);
        time.adicionarJogador(jogador2);

        System.out.println("Média de idade dos jogadores: " + time.calcularMediaDeIdadeDosJogadores());
        time.exibirTodasAsInformacoes();
    }
}
```

[Voltar](../../README.md)
