# Pacote jakarta.validation.constraints

O pacote `jakarta.validation.constraints` contém todas as restrições fornecidas pelo Jakarta Bean Validation, também chamadas de **restrições internas**. Essas restrições são usadas para validar propriedades de objetos em aplicações Java, garantindo que os dados atendam a critérios específicos.

---

### Enumerações

| Enumeração     | Descrição                                                          |
| -------------- | ------------------------------------------------------------------ |
| `Pattern.Flag` | Define possíveis flags para expressões regulares (_Regexp flags_). |

---

### Tipos de Anotações

| Anotação           | Descrição                                                                                    |
| ------------------ | -------------------------------------------------------------------------------------------- |
| `@AssertFalse`     | O elemento anotado deve ser `false`.                                                         |
| `@AssertTrue`      | O elemento anotado deve ser `true`.                                                          |
| `@DecimalMax`      | O elemento anotado deve ser um número cujo valor seja menor ou igual ao máximo especificado. |
| `@DecimalMin`      | O elemento anotado deve ser um número cujo valor seja maior ou igual ao mínimo especificado. |
| `@Digits`          | O elemento anotado deve ser um número dentro de um intervalo aceito.                         |
| `@Email`           | A string anotada deve ser um endereço de e-mail bem formado.                                 |
| `@Future`          | O elemento anotado deve ser um instante, data ou hora no futuro.                             |
| `@FutureOrPresent` | O elemento anotado deve ser um instante, data ou hora no presente ou no futuro.              |
| `@Max`             | O elemento anotado deve ser um número cujo valor seja menor ou igual ao máximo especificado. |
| `@Min`             | O elemento anotado deve ser um número cujo valor seja maior ou igual ao mínimo especificado. |
| `@Negative`        | O elemento anotado deve ser um número estritamente negativo.                                 |
| `@NegativeOrZero`  | O elemento anotado deve ser um número negativo ou igual a 0.                                 |
| `@NotBlank`        | O elemento anotado não deve ser nulo e deve conter pelo menos um caractere não em branco.    |
| `@NotEmpty`        | O elemento anotado não deve ser nulo nem vazio.                                              |
| `@NotNull`         | O elemento anotado não deve ser nulo.                                                        |
| `@Null`            | O elemento anotado deve ser nulo.                                                            |
| `@Past`            | O elemento anotado deve ser um instante, data ou hora no passado.                            |
| `@PastOrPresent`   | O elemento anotado deve ser um instante, data ou hora no passado ou no presente.             |
| `@Pattern`         | A sequência de caracteres anotada deve corresponder à expressão regular especificada.        |
| `@Positive`        | O elemento anotado deve ser um número estritamente positivo.                                 |
| `@PositiveOrZero`  | O elemento anotado deve ser um número positivo ou igual a 0.                                 |
| `@Size`            | O tamanho do elemento anotado deve estar entre os limites especificados (incluso).           |

> [!NOTE]
>
> Para todas as anotações mencionadas acima, existe uma variante com o sufixo `.List`. Essas variantes são usadas para definir múltiplas instâncias da mesma anotação em um único elemento. Isso é útil quando você precisa aplicar a mesma restrição com parâmetros diferentes no mesmo campo. Exemplos: `@AssertFalse.List`, `@NegativeOrZero.List` e `@Size.List`.

---

Referência: [Documentação oficial do Java](https://jakarta.ee/specifications/bean-validation/3.0/apidocs/jakarta/validation/constraints/package-summary)
