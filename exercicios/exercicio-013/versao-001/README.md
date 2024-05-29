# Exercício Java: Filtragem e mapeamento de dados

[Voltar](../../../README.md)

Neste exercício, você deverá criar uma aplicação em Java que utilize interfaces funcionais e Streams, aplicando uma maior variedade de tipos. Siga as instruções detalhadas abaixo:

1. Defina cinco funções baseadas nas interfaces funcionais do Java:

   - Uma função que recebe uma string e retorna o comprimento da string mais um.
   - Um predicado que retorna verdadeiro se o comprimento da string (use a função acima) for maior ou igual a 8.
   - Um predicado que retorna verdadeiro se o primeiro caractere da string for diferente do último.
   - Um operador unário que converte a string para maiúsculas e adiciona um ponto de exclamação no final.
   - Um predicado que retorna verdadeiro se a primeira letra da string for uma vogal.
   - Um consumidor que imprime a string no formato "Fruta: " seguido pelo nome da fruta.rima os valores no console com "Fruta: " antes de cada elemento.

2. Crie uma lista de strings contendo os elementos: `["laranja", "banana", "abacaxi", "uva", "kiwi", "melancia", "acerola", "morango", "ameixa", "jabuticaba", "umbu-cajá"]`.

3. Obtenha um `Stream` a partir da lista de strings e armazene-o em uma variável.

4. Aplique as seguintes operações no stream, utilizando as funções criadas:

   - As frutas são filtradas (`filter`) por meio do predicado, mantendo apenas aquelas com comprimento maior ou igual a 8.
   - Em seguida, as frutas são novamente filtradas (`filter`) usando o predicado, mantendo apenas aquelas em que o primeiro e o último caracteres são diferentes.
   - Depois, cada fruta é transformada (`map`) pelo operador unário, que as converte para maiúsculas e adiciona um ponto de exclamação no final.
   - As frutas resultantes são filtradas (`filter`) usando o predicado, mantendo apenas aquelas em que a primeira letra é uma vogal.
   - Por fim, cada fruta é impressa no console com o consumidor (`forEach`).

[Voltar](../../../README.md)
