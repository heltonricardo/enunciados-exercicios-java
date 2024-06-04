# Exercício Java: Filtragem e mapeamento de músicas

[Voltar](../../../README.md)

Neste exercício, você deverá criar uma aplicação em Java que utilize interfaces funcionais e Streams, aplicando operações diretamente nas lambdas dentro de `map` e `filter`. Além disso, você deverá criar uma classe `Musica` para representar os objetos nos quais as operações serão realizadas, e um `enum` para representar os gêneros musicais. Siga as instruções detalhadas abaixo:

1. Crie um `enum` chamado `Genero` com os seguintes valores:

   - `ROCK`
   - `POP`
   - `JAZZ`
   - `CLASSICA`

2. Crie uma classe `Musica` com os seguintes atributos privados:

   - `String titulo`
   - `String artista`
   - `int duracaoEmSegundos`
   - `Genero genero`

3. Crie um construtor com todos os atributos e um método `toString` no formato "Música: [Título] - [Duração em Minutos] minutos".

4. Instancie uma lista de músicas com pelo menos 10 objetos `Musica`, cada um com valores diferentes para os atributos.

5. Obtenha um `Stream` a partir da lista de músicas.

6. Aplique as seguintes operações no stream, utilizando lambdas diretamente nas chamadas de `map` e `filter`:

   - Filtre (`filter`) as músicas cuja duração seja maior ou igual a 250 segundos.
   - Filtre (`filter`) as músicas do gênero `ROCK`.
   - Mapeie (`map`) as músicas para um objeto que contenha apenas o título e a duração convertida de segundos para minutos.
   - Filtre (`filter`) as músicas cujo título tenha mais de uma palavra.
   - Ordene (`sorted`) as músicas por duração em ordem decrescente.
   - Imprima cada música (`forEach`) resultante no console usando o `toString` da classe.

7. A implementação deve ser feita utilizando lambdas diretamente nas operações do stream.

[Voltar](../../../README.md)
