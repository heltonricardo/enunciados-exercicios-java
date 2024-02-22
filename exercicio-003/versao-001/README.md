# Projeto Java: Sistema de gerenciamento de filmes

Este projeto Java tem como objetivo criar um sistema de gerenciamento de filmes, incorporando classes para atores, diretores, críticos e outras entidades, com ênfase em funcionalidades avançadas que aprimoram o sistema.

> ⚠ Sob construção

[Voltar](../../README.md)

# Índice

<!-- TOC -->

- [1. Descrição](#1-descri%C3%A7%C3%A3o)
- [2. Componentes](#2-componentes)
- [3. Requisitos](#3-requisitos)

<!-- /TOC -->

## 1. Descrição

Este projeto visa criar um sistema de gerenciamento de filmes em Java, abordando entidades essenciais do mundo cinematográfico, como Filmes, Diretores, Atores, Avaliações de Filmes, entre outros. O sistema oferece uma estrutura robusta para organização e manipulação de informações relacionadas aos filmes.

A implementação não se limita apenas à modelagem das classes, mas também prioriza a entrega de um conjunto de funcionalidades avançadas que enriquecem e aprimoram o sistema como um todo.

## 2. Componentes

```mermaid
classDiagram

class Pessoa {
  <<Abstract>>
  -String nome
  #Integer idade
  +String getNome()
  +void setNome(String nome)
  +Integer getIdade()
  +void setIdade(Integer idade)
  +String toString()
}

class VeiculoDeCritica {
  <<Enumeration>>
  SITE,
  REVISTA,
  JORNAL,
  CANAL_YOUTUBE,
  PODCAST
  +String toString()
}

class Classificacao {
  <<Enumeration>>
  LIVRE
  MAIOR_10
  MAIOR_12
  MAIOR_14
  MAIOR_16
  MAIOR_18
  +String toString()
}

class Genero {
  <<Enumeration>>
  ACAO
  AVENTURA
  COMEDIA
  DRAMA
  FICCAO_CIENTIFICA
  HORROR
  ROMANCE
  SUSPENSE
  OUTRO
  +String toString()
}

class Ator {
  <<Abstract>>
  -Genero generoPrincipal
  +Genero getGeneroPrincipal()
  +void setGeneroPrincipal(Genero generoPrincipal)
  +String toString()
}

class AtorPrincipal {
  -Integer anosDeExperiencia
  +Integer getAnosDeExperiencia()
  +void setAnosDeExperiencia(Integer anosDeExperiencia)
  +String toString()
}

class AtorCoadjuvante {
  -Double grauDeFama
  +Double getGrauDeFama()
  +void setGrauDeFama(Double grauDeFama)
  +String toString()
}

class Critico {
  -VeiculoDeCritica veiculoDeCritica
  +VeiculoDeCritica getVeiculoDeCritica()
  +void setVeiculoDeCritica(VeiculoDeCritica veiculoDeCritica)
  +String toString()
}

class Diretor {
  -String nacionalidade
  +String getNacionalidade()
  +void setNacionalidade(String nacionalidade)
  +String toString()
}

class Estudio {
  -String nome
  -Boolean independente
  -List < Avaliacao > avaliacoes
  -void setAvaliacoes(List < Avaliacao > avaliacoes)
  +String getNome()
  +void setNome(String nome)
  +Boolean isIndependente()
  +void setIndependente(Boolean independente)
  +List < Avaliacao > getAvaliacoes()
  +String toString()
}

class Filme {
  -String titulo
  -Duration tempoDeDuracao;
  -LocalDateTime dataHorarioDeLancamento;
  -Diretor diretor
  -Genero genero
  -Estudio estudio
  -List < Ator > elenco
  -List < Avaliacao > avaliacoes
  -void setElenco(List < Ator > elenco)
  -void setAvaliacoes(List < Avaliacao > avaliacoes)
  +String getTitulo()
  +void setTitulo(String titulo)
  +Duration getTempoDeDuracao()
  +void setTempoDeDuracao(Duration tempoDeDuracao)
  +LocalDate getDataHorarioDeLancamento()
  +void setDataHorarioDeLancamento(LocalDate DataHorarioDeLancamento)
  +Diretor getDiretor()
  +void setDiretor(Diretor diretor)
  +Genero getGenero()
  +void setGenero(Genero genero)
  +Estudio getEstudio()
  +void setEstudio(Estudio estudio)
  +List < Ator > getElenco()
  +List < Avaliacao > getAvaliacoes()
  +void adicionarAtor(Ator ator)
  +void exibirInformacoes()
}

class Avaliavel {
  <<Interface>>
  +void adicionarAvaliacao(Avaliacao avaliacao)
  +void limparAvaliacoes()
  +Double calcularMediaAvaliacoes()
}

class Avaliacao {
  -Critico critico
  -Double pontuacao
  +Critico getCritico()
  +void setCritico(Critico critico)
  +Double getPontuacao()
  +void setPontuacao(Double pontuacao)
  +String toString()
}

Pessoa <|-- Ator
Pessoa <|-- Diretor
Pessoa <|-- Critico

Ator <|-- AtorPrincipal
Ator <|-- AtorCoadjuvante

Avaliavel <.. Estudio
Avaliavel <.. Filme
```

## 3. Requisitos

Faça **validações**, garantindo que:

1. A idade dos diretores e críticos seja maior ou igual a **18** anos;
1. A idade dos atores seja maior ou igual a **5** anos. Para isso, sobrescreva o `setIdade` da superclasse;
1. O grau de fama dos atores coadjuvantes esteja dentro do intervalo de **0.0** a **10.0**;
1. A nacionalidade dos diretores não seja nula, vazia ou apenas espaços em branco;
1. O título dos filmes não seja nulo, vazio ou apenas espaços em branco;
1. O tempo de duração dos filmes seja positivo;
1. A data de lançamento dos filmes seja anterior ou igual à data atual;
1. O nome do estúdio dos filmes não seja nulo, vazio ou apenas espaços em branco;
1. A pontuação das avaliações dos filmes esteja dentro do intervalo de **0.0** a **10.0**;
1. O atributo de independência dos estúdios seja um valor verdadeiro ou falso;
1. O número de anos de experiência dos atores principais seja positivo;
1. Cada filme possua pelo menos um diretor associado;
1. Cada filme possua pelo menos um ator principal;
1. Cada estúdio possua um nome exclusivo, sem repetições;
1. Cada filme possua um título único, sem repetições;
1. Cada ator possua um nome exclusivo, sem repetições;
1. Cada diretor possua um nome exclusivo, sem repetições;

> ⚠ Sob construção

[Voltar](../../README.md)
