# Exercício: Exceções 3

## 1. Descrição

Você foi contratado para prototipar a estrutura básica de um estoque de uma empresa. Sua tarefa é implementar a lógica para garantir a integridade dos dados dos produtos, seguindo as seguintes regras:

- Cada produto tem um nome, uma quantidade e um preço unitário.
- O nome de um produto não pode estar em branco. Se um nome em branco for fornecido ao criar ou alterar um produto, uma exceção personalizada `NomeException` deve ser lançada, contendo uma mensagem explicativa para ser apresentada ao usuário.
- O preço unitário de um produto não pode ser zero ou negativo. Caso seja fornecido um preço incorreto ao criar ou alterar um produto, uma exceção personalizada `PrecoException` deve ser lançada, contendo uma mensagem explicativa para ser apresentada ao usuário.
- A quantidade de um produto não pode ser negativa. Se uma quantidade negativa for fornecida ao criar ou alterar um produto, uma exceção personalizada `QuantidadeException` deve ser lançada, contendo uma mensagem explicativa para ser apresentada ao usuário.
- Antes de adicionar um novo produto ao estoque, seja realizada uma operação de registro em um arquivo de log para manter um histórico de todas as operações de adição de produtos, independentemente do sucesso ou falha da operação.

> **`Pontos de atenção`**
>
> - Certifique que os atributos da classe `Produto` sejam privados.
> - Implemente os métodos `getters` e `setters` necessários para acessar e modificar os atributos da classe `Produto` e faça com que os `setters` lancem as exceções citadas anteriormente, quando necessário.
> - Implemente um construtor na classe `Produto` que recebe o nome, a quantidade e o preço unitário como parâmetros e inicializa os atributos da classe através dos `setters`.
> - Crie uma classe exclusivamente para lidar com os logs e utilize o `try-with-resources` para garantir o fechamento do arquivo.
> - Qualquer êxitos ou falhas ao criar/alterar um produto devem ser registradas no arquivo de log.

[Voltar](../../README.md)
