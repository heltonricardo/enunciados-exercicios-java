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
  - [2.1. De aplicação](#21-de-aplica%C3%A7%C3%A3o)
  - [2.2. De desenvolvimento](#22-de-desenvolvimento)
  - [2.3. De teste](#23-de-teste)
  - [2.4. De documentação](#24-de-documenta%C3%A7%C3%A3o)
- [3. Configurações](#3-configura%C3%A7%C3%B5es)
- [4. Entidades](#4-entidades)
- [5. Requisitos](#5-requisitos)
- [6. Estrutura do projeto](#6-estrutura-do-projeto)
- [7. Validações](#7-valida%C3%A7%C3%B5es)
- [8. Endpoints](#8-endpoints)
- [9. Testes](#9-testes)
  - [9.1. Estrutura de diretórios](#91-estrutura-de-diret%C3%B3rios)
  - [9.2. Configurações](#92-configura%C3%A7%C3%B5es)
  - [9.3. Mocks](#93-mocks)
- [10. Conclusão](#10-conclus%C3%A3o)

<!-- /TOC -->

## 1. Introdução

O projeto **Movepass** consiste em uma API REST que simula a gestão de academias, empresas e assinaturas de funcionários. A ideia central é permitir que empresas possam cadastrar seus funcionários em academias, gerenciando assinaturas e possibilitando que esses funcionários utilizem as academias parceiras.

Você precisará implementar quatro principais entidades: Empresa, Funcionário, Academia e Assinatura. A regra de negócio básica é que:

- Uma empresa pode ter vários funcionários, mas cada funcionário trabalha para uma única empresa.
- Um funcionário pode ter várias assinaturas para acessar diferentes academias.
- Uma academia pode ter várias assinaturas, cada uma vinculada a um funcionário diferente.

## 2. Dependências

Dependências de um projeto são bibliotecas externas ou módulos que o projeto precisa para funcionar corretamente, como frameworks, APIs ou ferramentas de suporte. Elas podem ser gerenciadas automaticamente por ferramentas como Maven, que baixam, atualizam e integram essas dependências ao projeto conforme especificado na configuração do build.

> [!IMPORTANT]
> Adicione as dependências de **`aplicação`**, **`desenvolvimento`** e **`teste`** no _Spring Initializr_ ao criar o projeto. Para as de **`documentação`**, adicione manualmente no `pom.xml`, pois, neste caso, a dependência requisitada não está disponível no _Spring Initializr_.

### 2.1. De aplicação

Dependências de aplicação são bibliotecas necessárias para a execução do software em produção, como frameworks e APIs essenciais para as funcionalidades principais.

- **MySQL Driver**: Driver JDBC para conectar o Spring Boot a um banco de dados MySQL.
- **Spring Data JPA**: Abstração do Spring sobre o JPA para simplificar o acesso e manipulação de dados em bancos de dados relacionais.
- **Spring Web**: Dependência que inclui suporte para o desenvolvimento de aplicações web, incluindo RESTful APIs.
- **Validation**: Suporte para validação de dados utilizando Jakarta Bean Validation (antigo Java Bean Validation).

### 2.2. De desenvolvimento

Dependências de desenvolvimento são ferramentas e bibliotecas usadas apenas durante o desenvolvimento do projeto, como linters, geradores de código ou plugins de integração.

- **Lombok**: Biblioteca que reduz o código boilerplate em classes. Através de simples anotações, gera métodos como getters, setters, equals, hashCode, toString, construtores e mais.
- **Spring Boot DevTools**: Ferramentas de desenvolvimento para acelerar o ciclo de feedback durante o desenvolvimento, como reinicialização automática e live reload.

### 2.3. De teste

Dependências de teste são bibliotecas usadas para escrever e executar testes automatizados, como frameworks de testes unitários, mocks ou ferramentas de cobertura de código.

- **Spring Boot Starter Test**: Framework de teste para escrever e executar testes unitários e de integração (já incluso por padrão ao gerar um projeto via _Spring Initializr_).

### 2.4. De documentação

Dependências de documentação são ferramentas utilizadas para gerar, gerenciar e publicar a documentação do projeto, como geradores de documentação a partir de comentários no código ou ferramentas de formatação de documentos.

- **OpenAPI**: Biblioteca para gerar e expor a documentação da API REST. Permite visualizar e interagir com a API de forma gráfica através de uma interface web implementada pelo Swagger. Por padrão, a documentação fica disponível em `GET /swagger-ui`.

  ```xml
   <dependency>
      <groupId>org.springdoc</groupId>
      <artifactId>springdoc-openapi-starter-webmvc-ui</artifactId>
      <version>2.6.0</version>
   </dependency>
  ```

  > :bulb: **Tip:** No próximo passo, usaremos uma configuração para que seja possível acessar a página do Swagger também através do endpoint `GET /docs`

## 3. Configurações

Estas configurações definem a conexão com o banco de dados MySQL, as credenciais de acesso e as propriedades do JPA para o projeto **Movepass**. Incluem parâmetros essenciais para garantir a persistência dos dados e o comportamento adequado da aplicação durante a execução. Insira esses valores no arquivo `application.properties`:

```properties
spring.jpa.open-in-view=false
springdoc.swagger-ui.path=/docs
spring.datasource.username=root
spring.datasource.password=12345678
spring.jpa.hibernate.ddl-auto=update
spring.datasource.url=jdbc:mysql://localhost:3306/movepass?createDatabaseIfNotExist=true
```

## 4. Entidades

As entidades do projeto **Movepass** representam os principais elementos do sistema, como Empresa, Funcionário, Academia e Assinatura. Abaixo está uma representação das classes dessas entidades:

```mermaid
classDiagram

class Academia {
  -Long id
  -String nome
  -String endereco
  -Boolean ativo
  -List< Assinaturas > assinaturas
  +Academia()
  +getters()
  +setters()
}

class Assinatura {
  -Long id
  -LocalDate dataInicio
  -LocalDate dataTermino
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
  -Boolean ativo
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
  -Boolean ativo
  -Empresa empresa
  -List< Assinatura > assinaturas
  +Funcionario()
  +getters()
  +setters()
}

Academia --* Assinatura
Empresa --* Funcionario
Funcionario --* Assinatura
```

## 5. Requisitos

Requisitos que devem ser seguidos ao implementar o exercício:

1. Certifique-se de que a lógica de soft delete seja implementada de forma consistente, filtrando registros inativos em qualquer consulta. **Soft delete** consiste na exclusão lógica de registros no banco de dados. Em vez de remover os registros fisicamente, um campo booleano (neste caso o campo `ativo`) será utilizado para indicar se o registro está ativo ou inativo.

2. As respostas da API podem utilizar as próprias entidades, embora seja recomendado usar DTOs de saída. Para as entradas, deve-se usar DTOs de entrada, solicitando apenas os dados necessários do cliente da aplicação.

3. Utilize anotações para melhorar a visualização da documentação no Swagger UI, como:

   - Anotar o classe controladora com `@Tag(name = "Nome do grupo de endpoints", description = "Descrição do grupo de endpoints")` (_io.swagger.v3.oas.annotations.tags.Tag_);
   - Anotar cada método da classe controladora com `@Operation(summary = "Resumo da operação", description = "Descrição detalhada da operação")` (_io.swagger.v3.oas.annotations.Operation_).

4. Lance exceções personalizadas quando necessário e capture-as na camada de controle usando um método anotado com `@ExceptionHandler(ClasseException.class)` (_org.springframework.web.bind.annotation.ExceptionHandler_).

5. Padronize todas as respostas das classes controladoras usando `ResponseEntity<Classe>` (_org.springframework.http.ResponseEntity_). Lembre-se de usar os códigos de status corretamente para cada método (vide [MOZILLA, Códigos de status de respostas HTTP](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Status)). Para facilitar, faça uso do enum `HttpStatus` (_org.springframework.http.HttpStatus_).

## 6. Estrutura do projeto

A estrutura principal do projeto **Movepass** segue uma organização modular, separando as responsabilidades de cada camada do sistema. Isso facilita a manutenção e a escalabilidade do código. Abaixo está a estrutura sugerida:

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
├─── exception
│    └─── RegistroInexistenteException.java
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
> Não esqueça de usar a anotação `@Valid` (_jakarta.validation.Valid_) nos parâmetros das _controllers_ para que as validações funcionem corretamente.

## 8. Endpoints

Crie endpoints para realizar as operações básicas de CRUD (Create, Read, Update, Delete) para cada entidade. Cada endpoint deve seguir o padrão RESTful, utilizando os métodos HTTP adequados:

- **Academia**

  - `POST /academias`: Criar nova academia.
  - `GET /academias`: Listar todas as academias.
  - `GET /academias/{academiaId}`: Obter detalhes de uma academia específica.
  - `PUT /academias/{academiaId}`: Atualizar dados de uma academia.
  - `DELETE /academias/{academiaId}`: Inativar uma academia (soft delete).

- **Assinatura**

  - `POST /assinaturas`: Criar nova assinatura.
  - `GET /assinaturas`: Listar todas as assinaturas.
  - `GET /assinaturas/{assinaturaId}`: Obter detalhes de uma assinatura específica.

- **Empresa**

  - `POST /empresas`: Criar nova empresa.
  - `POST /empresas/{empresaId}/funcionarios`: Criar novo funcionário na empresa.
  - `GET /empresas`: Listar todas as empresas.
  - `GET /empresas/{empresaId}`: Obter detalhes de uma empresa específica.
  - `GET /empresas/{empresaId}/funcionarios`: Listar todos os funcionários da empresa.
  - `PUT /empresas/{empresaId}`: Atualizar dados de uma empresa.
  - `DELETE /empresas/{empresaId}`: Inativar uma empresa (soft delete).

- **Funcionário**

  - `GET /funcionarios`: Listar todos os funcionários.
  - `GET /funcionarios/{funcionarioId}`: Obter detalhes de um funcionário específico.
  - `PUT /funcionarios/{funcionarioId}`: Atualizar dados de um funcionário.
  - `DELETE /funcionarios/{funcionarioId}`: Inativar um funcionário (soft delete).

## 9. Testes

Para garantir a qualidade do código e o funcionamento correto da aplicação, realizaremos **testes unitários**. Utilizaremos a biblioteca **Spring Boot Starter Test**, que já vem incluída por padrão quando geramos um projeto no _Spring Initializr_, para realizar esses testes unitários e assegurar que cada componente do sistema esteja funcionando como esperado.

> [!NOTE]
>
> **Testes unitários x Testes de integração**
>
> **Testes Unitários:** Focam em testar componentes individuais de um sistema (como métodos ou funções) de forma isolada, garantindo que cada parte funcione corretamente por si só. O objetivo é verificar a lógica interna de uma unidade de código sem depender de outros módulos ou partes do sistema. Usam mocks para substituir dependências externas.
>
> **Testes de Integração:** Avaliam a interação entre múltiplos componentes ou módulos do sistema. O foco é garantir que diferentes partes (como camadas de serviço, repositórios etc.) funcionem corretamente juntas. Esses testes verificam se a comunicação e integração entre essas partes ocorrem conforme o esperado.

### 9.1. Estrutura de diretórios

Para manter a organização, a estrutura de diretórios de testes deve espelhar a estrutura usada em `src/main`. Ou seja, cada classe em `src/main` terá uma classe de teste correspondente em `src/test`. As classes de teste devem ter o sufixo `Test` por convenção. Exemplo:

- **Classe principal (`src/main`)**: `src/main/java/com/projeto/service/MeuService.java`
- **Classe de teste (`src/test`)**: `src/test/java/com/projeto/service/MeuServiceTest.java`

### 9.2. Configurações

Cada classe de teste deve ser anotada com `@SpringBootTest` (_org.springframework.boot.test.context.SpringBootTest_). Isso indica que o contexto do Spring será carregado durante a execução dos testes. Além disso, cada método de teste deve ser anotado com `@Test` (_org.junit.jupiter.api.Test_):

```java
@SpringBootTest
public class ClasseComTestes {

    @Test
    public void metodoTeste1() {
    }

    @Test
    public void metodoTeste2() {
    }
}
```

### 9.3. Mocks

Mocks simulam o comportamento de objetos reais, permitindo focar no comportamento da unidade sob teste. Usamos a biblioteca **Mockito** para criar mocks. A anotação `@MockBean` substitui um bean no contexto do Spring por um mock durante os testes.

**Exemplo: Testando um serviço de e-mail**

Vamos considerar um cenário em que temos um serviço de notificação (`ServicoDeNotificacao`) que utiliza um componente externo (`EnviadorDeEmail`) para enviar e-mails. Queremos testar apenas o comportamento do `ServicoDeNotificacao` sem depender da implementação real de envio de e-mails.

```java
// Classe a ser testada

@Service
public class ServicoDeNotificacao {

    @Autowired
    private final EnviadorDeEmail enviadorDeEmail;

    public boolean enviarEmailDeBoasVindas(String enderecoEmail) {
        String mensagem = "Bem-vindo à nossa plataforma!";
        return enviadorDeEmail.enviarEmail(enderecoEmail, mensagem);
    }
}
```

```java
// Teste unitário com Mock

@SpringBootTest
public class ServicoDeNotificacaoTest {

    @Autowired
    private ServicoDeNotificacao servicoDeNotificacao;

    @MockBean
    private EnviadorDeEmail enviadorDeEmail;

    @Test
    public void deveEnviarEmailDeBoasVindas() {
        Mockito.when(enviadorDeEmail.enviarEmail("usuario@exemplo.com", "Bem-vindo à nossa plataforma!"))
               .thenReturn(true);

        boolean resultado = servicoDeNotificacao.enviarEmailDeBoasVindas("usuario@exemplo.com");

        Assertions.assertTrue(resultado);

        Mockito.verify(enviadorDeEmail, Mockito.times(1))
               .enviarEmail("usuario@exemplo.com", "Bem-vindo à nossa plataforma!");
    }
}
```

Neste exemplo:

- `@MockBean` cria um mock de `EnviadorDeEmail` no contexto de teste.
- O mock é configurado para simular o retorno de `true` quando o método `enviarEmail` é chamado com parâmetros específicos.
- Testamos o método `enviarEmailDeBoasVindas` de `ServicoDeNotificacao` e verificamos se ele retorna o valor esperado (`true`).
- Além disso, usamos `Mockito.verify` para garantir que o método `enviarEmail` foi chamado exatamente uma vez com os argumentos corretos.

## 10. Conclusão

Ao concluir o desenvolvimento do projeto **Movepass**, você terá criado uma API REST funcional para a gestão de academias e assinaturas utilizando Java e Spring Boot. Este exercício proporcionou uma valiosa oportunidade para aplicar conceitos essenciais de Programação Orientada a Objetos (POO), implementar testes unitários e seguir boas práticas de desenvolvimento de software, consolidando assim suas habilidades técnicas e aprimorando sua experiência no desenvolvimento de APIs.

[Voltar](../../../README.md)
