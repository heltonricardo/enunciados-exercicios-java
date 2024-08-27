# Exercício Java: Movepass

<p align="center">
  <a href="#">
    <img src="./logo.png" alt="Logo Movepass" />
  </a>
</p>

Neste exercício, você desenvolverá uma API REST utilizando Java e Spring Boot, com foco na criação de um sistema simples chamado **Movepass**. Este sistema é inspirado no Gympass, e será utilizado para praticar conceitos de Programação Orientada a Objetos (POO), testes, Spring Boot, e boas práticas de desenvolvimento de software.

[Voltar](../../../README.md)

# Índice

<!-- TOC -->

- [1. Introdução](#1-introdu%C3%A7%C3%A3o)
- [2. Dependências](#2-depend%C3%AAncias)
- [3. Configurações](#3-configura%C3%A7%C3%B5es)
- [4. Entidades](#4-entidades)
- [5. Restrições](#5-restri%C3%A7%C3%B5es)
- [6. Estrutura do projeto](#6-estrutura-do-projeto)
- [7. Validações](#7-valida%C3%A7%C3%B5es)
- [8. Endpoints](#8-endpoints)
- [9. Conclusão](#9-conclus%C3%A3o)

<!-- /TOC -->

## 1. Introdução

O projeto **Movepass** consiste em uma API REST que simula a gestão de academias, empresas e assinaturas de funcionários. A ideia central é permitir que empresas possam cadastrar seus funcionários em academias, gerenciando assinaturas e possibilitando que esses funcionários utilizem as academias parceiras.

Você precisará implementar quatro principais entidades: Empresa, Funcionário, Academia e Assinatura. A regra de negócio básica é que uma empresa pode ter múltiplos funcionários, cada funcionário pode ter uma assinatura em uma ou mais academias, e cada academia pode ter vários funcionários assinantes.

Além disso, este exercício visa a implementação de **soft delete**, que consiste na exclusão lógica de registros no banco de dados. Em vez de remover os registros fisicamente, um campo booleano (por exemplo, `ativo`) será utilizado para indicar se o registro está ativo ou inativo.

## 2. Dependências

Adicione as seguintes dependências ao seu arquivo `pom.xml` para configurar o projeto:

- Para a aplicação:

  - **MySQL Driver**: Driver JDBC para conectar o Spring Boot a um banco de dados MySQL.
  - **Spring Boot DevTools**: Ferramentas de desenvolvimento para acelerar o ciclo de feedback durante o desenvolvimento, como reinicialização automática e live reload.
  - **Spring Data JPA**: Abstração do Spring sobre o JPA para simplificar o acesso e manipulação de dados em bancos de dados relacionais.
  - **Spring Web**: Dependência que inclui suporte para o desenvolvimento de aplicações web, incluindo RESTful APIs.
  - **Validation**: Suporte para validação de dados utilizando Jakarta Bean Validation (antigo Java Bean Validation).

- Para os testes:

  - **H2 Database**: Banco de dados em memória utilizado para testes, útil por ser leve e de fácil configuração.
  - **Spring Boot Starter Test**: Framework de teste para escrever e executar testes unitários e de integração (já incluso por padrão ao gerar um projeto via Spring Initializr).

- Para a documentação:

  ```xml
  <dependency>
      <groupId>org.springdoc</groupId>
      <artifactId>springdoc-openapi-ui</artifactId>
      <version>1.8.0</version>
  </dependency>
  ```

  Biblioteca para gerar e expor a documentação da API REST usando OpenAPI (anteriormente conhecido como Swagger). Permite visualizar e interagir com a API de forma gráfica através de uma interface web. Por padrão, a documentação fica disponível em `/swagger-ui/index.html`.

## 3. Configurações

Definem a conexão com o banco de dados MySQL, as credenciais de acesso e as propriedades do JPA para o projeto Movepass. Incluem parâmetros essenciais para garantir a persistência dos dados e o comportamento adequado da aplicação durante a execução.

```properties
spring.jpa.open-in-view=false
springdoc.swagger-ui.path=/docs
spring.datasource.username=root
spring.datasource.password=12345678
spring.jpa.hibernate.ddl-auto=update
spring.datasource.url=jdbc:mysql://localhost:3306/movepass?createDatabaseIfNotExist=true
```

## 4. Entidades

As entidades do projeto Movepass representam os principais elementos do sistema, como Empresa, Funcionário, Academia e Assinatura. Abaixo está uma representação das classes dessas entidades:

```mermaid
classDiagram

class Academia {
  -Long id
  -String nome
  -String endereco
  -Bool ativo
  +Academia()
  +getters()
  +setters()
}

class Assinatura {
  -Long id
  -LocalDate dataInicio
  -LocalDate dataTermino
  -Bool ativo
  -Academia academia
  -Funcionario funcionario
  +Assinatura()
  +getters()
  +setters()
}

class Empresa {
  -Long id
  -String cnpj
  -String nome
  -Bool ativo
  -List< Funcionario > funcionarios
  +Empresa()
  +getters()
  +setters()
}

class Funcionario {
  -Long id
  -String nome
  -String email
  -LocalDate dataContratacao
  -Bool ativo
  +Funcionario()
  +getters()
  +setters()
}
```

## 5. Restrições

1. Certifique-se de que a lógica de soft delete seja implementada de forma consistente, filtrando registros inativos nas consultas `GET` e reativando registros quando necessário, se isso fizer parte dos requisitos de negócio.

2. As respostas da API podem utilizar as próprias entidades, embora seja recomendado usar DTOs de saída. Para as entradas, deve-se usar DTOs de entrada, solicitando apenas os dados necessários do cliente da aplicação.

## 6. Estrutura do projeto

A estrutura do projeto Movepass segue uma organização modular, separando as responsabilidades de cada camada do sistema. Isso facilita a manutenção e a escalabilidade do código. Abaixo está a estrutura sugerida:

```text
src/main/java/com/movepass
├─── controller
│    ├─── AcademiaController.java
│    ├─── AssinaturaController.java
│    ├─── EmpresaController.java
│    └─── FuncionarioController.java
├─── dto
│    ├─── AcademiaDTO.java
│    ├─── AssinaturaDTO.java
│    ├─── EmpresaDTO.java
│    └─── FuncionarioDTO.java
├─── model
│    ├─── entity
│    │    ├─── Academia.java
│    │    ├─── Assinatura.java
│    │    ├─── Empresa.java
│    │    └─── Funcionario.java
│    └─── repository
│         ├─── AcademiaRepository.java
│         ├─── AssinaturaRepository.java
│         ├─── EmpresaRepository.java
│         └─── FuncionarioRepository.java
├─── service
│    ├─── AcademiaService.java
│    ├─── AssinaturaService.java
│    ├─── EmpresaService.java
│    └─── FuncionarioService.java
└─── MovepassApplication.java


src/test/java/com/movepass
└─── controller
     ├─── AcademiaControllerTest.java
     ├─── AssinaturaControllerTest.java
     ├─── EmpresaControllerTest.java
     └─── FuncionarioControllerTest.java
```

## 7. Validações

Utilize **Jakarta Constraints** para validar os dados recebidos do cliente. Por exemplo:

- **Funcionário**:

  - Nome (não nulo e com tamanho mínimo de 3 caracteres).
  - Email (não nulo e no formato correto).

- **Empresa**:

  - Nome da empresa (não nulo e com tamanho mínimo de 3 caracteres).
  - CNPJ (não nulo e no formato correto).

- **Academia**:

  - Nome da academia (não nulo e com tamanho mínimo de 3 caracteres).
  - Endereço (não nulo).

- **Assinatura**:

  - Data de início (não nula e não pode ser no passado).
  - Data de término (deve ser posterior à data de início).
  - Academia (não nula).

> [!TIP]
>
> As anotações para validação podem ser encontradas no arquivo [jakarta.validation.constraints.md](../../../util/jakarta.validation.constraints.md).

> [!WARNING]
>
> Não esqueça de usar a anotação `@Valid` nos parâmetros das _controllers_ para que a validação funcione corretamente.

## 8. Endpoints

Crie endpoints para realizar as operações básicas de CRUD (Create, Read, Update, Delete) para cada entidade. Cada endpoint deve seguir o padrão RESTful, utilizando os métodos HTTP adequados:

- **Academia**

  - `POST /academias`: Criar nova academia.
  - `GET /academias`: Listar todas as academias.
  - `GET /academias/{id}`: Obter detalhes de uma academia específica.
  - `PUT /academias/{id}`: Atualizar dados de uma academia.
  - `DELETE /academias/{id}`: Inativar uma academia (soft delete).

- **Assinatura**

  - `POST /assinaturas`: Criar nova assinatura.
  - `GET /assinaturas`: Listar todas as assinaturas.
  - `GET /assinaturas/{id}`: Obter detalhes de uma assinatura específica.
  - `PUT /assinaturas/{id}`: Atualizar dados de uma assinatura.
  - `DELETE /assinaturas/{id}`: Inativar uma assinatura (soft delete).

- **Empresa**

  - `POST /empresas`: Criar nova empresa.
  - `GET /empresas`: Listar todas as empresas.
  - `GET /empresas/{id}`: Obter detalhes de uma empresa específica.
  - `PUT /empresas/{id}`: Atualizar dados de uma empresa.
  - `DELETE /empresas/{id}`: Inativar uma empresa (soft delete).

- **Funcionário**

  - `POST /funcionarios`: Criar novo funcionário.
  - `GET /funcionarios`: Listar todos os funcionários.
  - `GET /funcionarios/{id}`: Obter detalhes de um funcionário específico.
  - `PUT /funcionarios/{id}`: Atualizar dados de um funcionário.
  - `DELETE /funcionarios/{id}`: Inativar um funcionário (soft delete).

## 9. Conclusão

Ao concluir o desenvolvimento do projeto **Movepass**, você terá criado uma API REST funcional para a gestão de academias e assinaturas, utilizando Java e Spring Boot. Este exercício ofereceu uma ótima oportunidade para praticar conceitos importantes de Programação Orientada a Objetos, além de testes e boas práticas de desenvolvimento de software. A implementação de soft delete e as validações com Jakarta Constraints garantem uma boa gestão dos dados e a integridade das informações.

A estrutura modular do projeto, com suas entidades, serviços e controllers bem definidos, facilita a manutenção e a escalabilidade do sistema. Este projeto não só aprimorou suas habilidades técnicas, mas também ofereceu uma experiência prática valiosa no desenvolvimento de APIs.

[Voltar](../../../README.md)
