# Exercício Java: Filtragem e mapeamento de músicas

[Voltar](../../../README.md)

Neste exercício, você deverá criar uma aplicação em Java que utilize interfaces funcionais e Streams, aplicando operações diretamente nas lambdas dentro de `filter`, `map`, `sorted` e `forEach`. Além disso, você deverá criar uma classe `Musica` e uma classe `MusicaMapper` para representar os objetos nos quais as operações serão realizadas, e um `enum` para representar os gêneros musicais. Siga as instruções detalhadas abaixo:

1. Crie um `enum` chamado `Genero` com os seguintes valores:

   - `CLASSICA`
   - `HIPHOP`
   - `JAZZ`
   - `POP`
   - `ROCK`

2. Crie uma classe `Musica` com os seguintes atributos privados:

   - `String titulo`
   - `String artista`
   - `int duracaoEmSegundos`
   - `Genero genero`

> [!NOTE]
>
> Implemente um construtor com todos os atributos.
>
> Implemente métodos getter e setter para cada atributo.

3. Crie uma classe `MusicaMapper` com os seguintes atributos privados:

   - `String titulo`
   - `double duracaoEmMinutos`

   E o seguinte método privado:

   - `double segundosParaMinutos` que recebe um valor inteiro em segundos e retorna o equivalente em minutos.

> [!NOTE]
>
> Implemente um construtor que aceite apenas um objeto `Musica` e extrai dele o que for necessário.
>
> Implemente métodos getter e setter para cada atributo. No getter da duração, retorne o valor com apenas duas casas decimais.
>
> Implemente um método `toString` no formato "Música: [Título] - [Duração em Minutos] minutos" (use os getters da classe).

4. Instancie uma lista de músicas em uma classe com método `main` com pelo menos 10 objetos `Musica`, cada um com valores diferentes para os atributos.

> [!TIP]
>
> - Hey Jude - The Beatles - 210 segundos - ROCK
> - Imagine - John Lennon - 180 segundos - POP
> - Like a Rolling Stone - Bob Dylan - 370 segundos - ROCK
> - Blue Train - John Coltrane - 220 segundos - JAZZ
> - Clair de Lune - Debussy - 240 segundos - CLASSICA
> - Hotel California - Eagles - 390 segundos - ROCK
> - Stairway to Heaven - Led Zeppelin - 480 segundos - ROCK
> - Purple Rain - Prince - 500 segundos - POP
> - Juicy - The Notorious B.I.G. - 360 segundos - HIPHOP
> - Let It Be - The Beatles - 230 segundos - ROCK

5. Obtenha um `Stream` a partir da lista criada, aplicando as seguintes operações:

   - Filtre (`filter`) as músicas cuja duração seja maior que 250 segundos.
   - Filtre (`filter`) as músicas do gênero `ROCK`.
   - Mapeie (`map`) as músicas para objetos `MusicaMapper`.
   - Filtre (`filter`) as músicas cujo título tenha mais de duas palavras.
   - Ordene (`sorted`) as músicas por duração em minutos em ordem decrescente.
   - Imprima cada música (`forEach`) resultante no console usando o `toString` da classe `MusicaMapper`.

[Voltar](../../../README.md)
