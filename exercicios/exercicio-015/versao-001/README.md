# Exercício Java: API REST com CRUD de Produtos

[Voltar](../../../README.md)

Desenvolver uma API funcional que permita realizar operações CRUD (Create, Read, Update, Delete) em produtos. A API deve implementar os seguintes endpoints:

-   `POST /produtos` - Criar um novo produto.
-   `GET /produtos` - Listar todos os produtos.
-   `GET /produtos/{id}` - Obter detalhes de um produto específico pelo seu ID.
-   `PUT /produtos/{id}` - Atualizar informações de um produto específico pelo seu ID.
-   `DELETE /produtos/{id}` - Deletar um produto específico pelo seu ID.

## Modelo de Produto

Um produto deve possuir os seguintes atributos:

-   `Long id`
-   `String descricao`
-   `Float preco`
-   `Boolean disponivel`
-   `Double peso`
-   `Character categoria`

Além disso, o modelo deve incluir um construtor vazio, getters e setters para todos os atributos.

## Configuração do Banco de Dados

Instale e configure o MySQL Community Edition.

## Criação do Projeto

Crie o projeto usando o Spring Initializr (https://start.spring.io/), adicionando as seguintes dependências:

-   **MySQL Driver**: Driver JDBC necessário para a conexão com o banco de dados MySQL.
-   **Spring Boot DevTools**: Ferramentas de desenvolvimento para facilitar o desenvolvimento e a depuração do aplicativo.
-   **Spring Data JPA**: Abstração de persistência que simplifica o acesso a bancos de dados relacionais e fornece uma implementação do JPA (Java Persistence API).
-   **Spring Web**: Facilita a criação de aplicativos web, incluindo RESTful APIs.

## Configuração do `application.properties`

No arquivo `application.properties`, insira as seguintes configurações básicas:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/api_produtos?createDatabaseIfNotExist=true
spring.datasource.username=root
spring.datasource.password=12345678
spring.jpa.hibernate.ddl-auto=update
spring.jpa.open-in-view=false
```

> [!NOTE]
>
> -   `spring.datasource.url`: URL de conexão JDBC para o banco de dados MySQL. O parâmetro createDatabaseIfNotExist=true garante que o banco de dados seja criado se não existir.
> -   `spring.datasource.username`: Nome de usuário para conectar ao banco de dados.
> -   `spring.datasource.password`: Senha para conectar ao banco de dados.
> -   `spring.jpa.hibernate.ddl-auto`: Configuração do Hibernate para controlar o comportamento de atualização do esquema do banco de dados. O valor update permite que o Hibernate atualize o esquema do banco de dados conforme as mudanças nas entidades.
> -   `spring.jpa.open-in-view=false`: Desativa a estratégia de Open Session in View. Isso pode melhorar o desempenho e evitar possíveis problemas de gerenciamento de transações além de remover o _warning_ quando a aplicação é executada.

## Estrutura do Projeto

```
src/main/java/com/seu_projeto/api
|-- resource
|   |-- ProdutoResource.java
|-- model
|   |-- entity
|   |   |-- Produto.java
|   |-- repository
|       |-- ProdutoRepository.java
|-- Application.java
```

[Voltar](../../../README.md)
