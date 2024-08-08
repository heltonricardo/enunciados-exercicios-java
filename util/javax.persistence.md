# Pacote javax.persistence

## Anotações de Relacionamento

| Anotação      | Descrição                                                                                                                                                                                                                                                |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `@ManyToOne`  | Define um relacionamento onde muitos objetos da entidade atual estão associados a um único objeto de outra entidade. É o lado "muitos" da relação.                                                                                                       |
| `@OneToMany`  | Define um relacionamento onde um único objeto da entidade atual está associado a muitos objetos de outra entidade. É o lado "um" da relação, e é comumente mapeado com um `@JoinColumn` ou `@MappedBy`.                                                  |
| `@OneToOne`   | Define um relacionamento de um para um, onde um objeto da entidade atual está associado a exatamente um objeto de outra entidade. Pode ser bidirecional ou unidirecional, e geralmente usa `@JoinColumn` para especificar a coluna de chave estrangeira. |
| `@ManyToMany` | Define um relacionamento muitos-para-muitos entre duas entidades. Em geral, requer uma tabela intermediária (ou tabela de junção) que contém as chaves estrangeiras de ambas as entidades.                                                               |

## Anotações de Configuração de Relacionamento

| Anotação                | Descrição                                                                                                                                                                                                                                                   |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `@JoinColumn`           | Especifica a coluna de junção (chave estrangeira) usada em relacionamentos `@OneToOne`, `@ManyToOne`, e `@OneToMany` (quando não se usa `@MappedBy`). Permite definir o nome da coluna, se é nullable, e outras propriedades.                               |
| `@JoinTable`            | Usada para definir uma tabela de junção intermediária em um relacionamento `@ManyToMany`, ou em um relacionamento `@OneToOne` ou `@ManyToOne` onde é necessária uma tabela intermediária personalizada. Especifica o nome da tabela e as colunas de junção. |
| `@MappedBy`             | Usada no lado inverso de um relacionamento bidirecional (`@OneToMany`, `@ManyToMany`, `@OneToOne`) para indicar que o mapeamento é gerenciado pelo atributo correspondente na outra entidade.                                                               |
| `@PrimaryKeyJoinColumn` | Utilizada em uma associação `@OneToOne` ou herança para indicar que a chave primária da entidade atual também é usada como chave estrangeira para outra entidade.                                                                                           |

## Anotações Complementares

| Anotação                | Descrição                                                                                                                                                                                                                          |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `@OrderBy`              | Define a ordenação dos elementos em uma coleção, aplicável a relacionamentos `@OneToMany` e `@ManyToMany`. A ordenação pode ser especificada com base em uma ou mais propriedades da entidade.                                     |
| `@OrderColumn`          | Usada para mapear uma coluna que mantém a ordem dos elementos em uma coleção, aplicável a relacionamentos `@OneToMany` e `@ManyToMany`. A coluna de ordenação pode ser persistida e atualizada para manter a ordem dos elementos.  |
| `@MapKey`               | Especifica a propriedade de uma entidade que será usada como chave em um mapa (`java.util.Map`) para relacionamentos como `@OneToMany` ou `@ManyToMany`.                                                                           |
| `@MapKeyColumn`         | Similar ao `@MapKey`, mas especifica uma coluna para a chave de um mapa, geralmente em um relacionamento `@ElementCollection` ou `@OneToMany`.                                                                                     |
| `@MapKeyJoinColumn`     | Define a coluna de chave estrangeira usada como chave de um mapa em um relacionamento `@ManyToMany` ou `@OneToMany`.                                                                                                               |
| `@MapKeyEnumerated`     | Especifica que o valor da chave de um mapa deve ser mapeado como um enumerado (`enum`).                                                                                                                                            |
| `@MapKeyTemporal`       | Especifica que o valor da chave de um mapa deve ser mapeado como um valor temporal (`java.util.Date` ou `java.util.Calendar`).                                                                                                     |
| `@ForeignKey`           | Define a estratégia para geração de chaves estrangeiras em relacionamentos. Esta anotação é usada em conjunto com outras, como `@JoinColumn`, para customizar aspectos das chaves estrangeiras, como nome e estratégia de criação. |
| `@AssociationOverride`  | Permite sobrescrever as configurações de associação (relacionamento) de uma entidade embutida (`@Embedded`) ou de uma entidade em uma classe herdada.                                                                              |
| `@AssociationOverrides` | Usada para aplicar múltiplos `@AssociationOverride` em uma entidade embutida ou em uma classe herdada.                                                                                                                             |
