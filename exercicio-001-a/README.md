# Projeto Java: Sistema de gerenciamento de times de futebol

## 1. Descrição

Este projeto visa criar um sistema de gerenciamento de times de futebol em Java, contemplando as principais entidades presentes em um ambiente esportivo. As classes principais incluem representações para Jogadores, Técnicos e Times, proporcionando uma estrutura coesa para a organização e manipulação de informações relacionadas ao mundo do futebol.

A implementação não se limita à modelagem das classes, mas também prioriza a entrega de um conjunto de funcionalidades que enriquecem e aprimoram o sistema como um todo.

## 2. Classes

### Jogador

- **Atributos**:
  - `nome`: String
  - `idade`: int
  - `posicao`: String
  - `salario`: float
  - `contratado`: boolean
- **Métodos**: construtores (com e sem parâmetros), métodos `get` e `set` para todos os atributos.

### Tecnico

- **Atributos**:
  - `nome`: String
  - `idade`: int
  - `salario`: float
  - `anosExperiencia`: int
- **Métodos**: construtores (com e sem parâmetros), métodos `get` e `set` para todos os atributos.

### Time

- **Atributos**:
  - `nome`: String
  - `cidade`: String
  - `anoFundacao`: int
  - `listaJogadores`: List\<Jogador\>
  - `tecnicoResponsavel`: Tecnico
- **Métodos**: construtores (com e sem parâmetros), métodos `get` e `set` para todos os atributos.

## 3. Requisitos

Faça **validações**, garantindo que:

- a idade dos jogadores e do técnico seja maior que zero;
- o salário não seja negativo para jogadores e técnicos;
- o ano de fundação do time seja um valor válido (por exemplo, não pode ser um ano futuro).

> Dica: faça as validações **antes** de atribuir os valores nos atributos!

## 4. Funcionalidades

- Crie um método na classe **Time** para calcular a média de idade dos jogadores do time.
- Implemente um método na classe **Time** para exibir todas as informações do time, incluindo o nome, cidade, ano de fundação, informações do técnico e a lista de jogadores.

## 5. Exemplo de uso

![](./assets/code.png)

[Voltar](../README.md)
