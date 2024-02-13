# Projeto Java: Sistema de gerenciamento de filmes

Este projeto Java tem como objetivo criar um sistema de gerenciamento de filmes, incorporando classes para atores, diretores, críticos e outras entidades, com ênfase em funcionalidades avançadas que aprimoram o sistema.

[Voltar](../../README.md)

# Índice

<!-- TOC -->

- [1. Descrição](#1-descri%C3%A7%C3%A3o)
- [2. Componentes](#2-componentes)

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
  -Integer idade
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
}

class Classificacao {
  <<Enumeration>>
  LIVRE
  MAIOR_10
  MAIOR_12
  MAIOR_14
  MAIOR_16
  MAIOR_18
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
  +String getNome()
  +void setNome(String nome)
  +Boolean isIndependente()
  +void setIndependente(Boolean independente)
  +List < Avaliacao > getAvaliacoes()
  -void setAvaliacoes(List < Avaliacao > avaliacoes)
  +String toString()
}

class Filme {
  -String titulo
  -LocalTime tempoDeDuracao;
  -LocalDate DataDeLancamento;
  -Diretor diretor
  -Genero genero
  -Estudio estudio
  -List < Ator > elenco
  -List < Avaliacao > avaliacoes
  -void setElenco(List < Ator > elenco)
  -void setAvaliacoes(List < Avaliacao > avaliacoes)
  +String getTitulo()
  +void setTitulo(String titulo)
  +LocalTime getTempoDeDuracao()
  +void setTempoDeDuracao(LocalTime tempoDeDuracao)
  +LocalDate getDataDeLancamento()
  +void setDataDeLancamento(LocalDate DataDeLancamento)
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

> ⚠ Sob construção

[Voltar](../../README.md)
