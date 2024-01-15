# Projeto Java: Sistema de gerenciamento de bandas de K-pop

## 1. Descrição

Este projeto tem como objetivo criar um sistema de gerenciamento de bandas de K-pop em Java, abrangendo as principais entidades presentes no cenário musical. As classes principais incluem representações para Membros, Managers e Bandas, proporcionando uma estrutura coesa para a organização e manipulação de informações relacionadas ao universo do K-pop.

A implementação não se limita apenas à modelagem das classes, mas também prioriza a entrega de um conjunto de funcionalidades que enriquecem e aprimoram o sistema como um todo.

## 2. Classes

### Membro

- **Atributos**:
  - `nome`: String
  - `idade`: int
  - `cargo`: String
  - `salario`: float
  - `statusContrato`: boolean
- **Métodos**: construtores (com e sem parâmetros), métodos `get` e `set` para todos os atributos.

### Manager

- **Atributos**:
  - `nome`: String
  - `idade`: int
  - `salario`: float
  - `anosExperiencia`: int
- **Métodos**: construtores (com e sem parâmetros), métodos `get` e `set` para todos os atributos.

### Banda

- **Atributos**:
  - `nome`: String
  - `agencia`: String
  - `anoDeEstreia`: int
  - `listaMembros`: List\<Membro\>
  - `managerResponsavel`: Manager
- **Métodos**: construtores (com e sem parâmetros), métodos `get` e `set` para todos os atributos.

## 3. Requisitos

Faça **validações**, garantindo que:

1. A idade dos membros e do manager seja maior que zero.
1. O salário não pode ser negativo para membros e managers.
1. O ano de estreia da banda seja um valor válido (por exemplo, não pode ser um ano futuro).

> Dica: faça as validações **antes** de atribuir os valores nos atributos!

## 4. Funcionalidades

1. Crie um método na classe **Banda** para calcular a média de idade dos membros da banda.
1. Implemente um método na classe **Banda** para exibir todas as informações da banda, incluindo o nome, agência, ano de estreia, informações do manager e a lista de membros.

## 5. Exemplo de uso

```java
public class Main {
    public static void main(String[] args) {
        Membro membro1 = new Membro("Jimin", 25, "Vocalista", 300000.0, true);
        Membro membro2 = new Membro("Jungkook", 24, "Maknae", 350000.0, true);

        Manager manager = new Manager("Bang Si-hyuk", 45, 1500000.0, 15);

        Banda banda = new Banda("BTS", "Big Hit Entertainment", 2013, manager);
        banda.adicionarMembro(membro1);
        banda.adicionarMembro(membro2);

        System.out.println("Média de idade dos membros: " + banda.calcularMediaIdade());
        banda.exibirInformacoes();
    }
}
```

[Voltar](../README.md)
