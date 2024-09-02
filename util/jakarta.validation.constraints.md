# Pacote jakarta.validation.constraints

O pacote `jakarta.validation.constraints` contém todas as restrições fornecidas pelo Jakarta Bean Validation, também chamadas de **restrições internas**. Essas restrições são usadas para validar propriedades de objetos em aplicações Java, garantindo que os dados atendam a critérios específicos.

---

### Enumerações

| Enumeração     | Descrição                                                          |
| -------------- | ------------------------------------------------------------------ |
| `Pattern.Flag` | Define possíveis flags para expressões regulares (_Regexp flags_). |

---

### Tipos de Anotações

| Anotação           | Tipos Anotáveis                                                                               | Descrição                                                                                    |
| ------------------ | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| `@AssertFalse`     | `Boolean`, `boolean`                                                                          | O elemento anotado deve ser `false`.                                                         |
| `@AssertTrue`      | `Boolean`, `boolean`                                                                          | O elemento anotado deve ser `true`.                                                          |
| `@DecimalMax`      | `BigDecimal`, `BigInteger`, `CharSequence`, `byte`, `short`, `int`, `long`, `double`, `float` | O elemento anotado deve ser um número cujo valor seja menor ou igual ao máximo especificado. |
| `@DecimalMin`      | `BigDecimal`, `BigInteger`, `CharSequence`, `byte`, `short`, `int`, `long`, `double`, `float` | O elemento anotado deve ser um número cujo valor seja maior ou igual ao mínimo especificado. |
| `@Digits`          | `BigDecimal`, `BigInteger`, `CharSequence`, `byte`, `short`, `int`, `long`                    | O elemento anotado deve ser um número dentro de um intervalo aceito.                         |
| `@Email`           | `String`, `CharSequence`                                                                      | A string anotada deve ser um endereço de e-mail bem formado.                                 |
| `@Future`          | `Date`, `Calendar`, `Instant`, `LocalDate`, `LocalDateTime`, `ZonedDateTime`                  | O elemento anotado deve ser um instante, data ou hora no futuro.                             |
| `@FutureOrPresent` | `Date`, `Calendar`, `Instant`, `LocalDate`, `LocalDateTime`, `ZonedDateTime`                  | O elemento anotado deve ser um instante, data ou hora no presente ou no futuro.              |
| `@Max`             | `BigDecimal`, `BigInteger`, `byte`, `short`, `int`, `long`                                    | O elemento anotado deve ser um número cujo valor seja menor ou igual ao máximo especificado. |
| `@Min`             | `BigDecimal`, `BigInteger`, `byte`, `short`, `int`, `long`                                    | O elemento anotado deve ser um número cujo valor seja maior ou igual ao mínimo especificado. |
| `@Negative`        | `BigDecimal`, `BigInteger`, `byte`, `short`, `int`, `long`, `double`, `float`                 | O elemento anotado deve ser um número estritamente negativo.                                 |
| `@NegativeOrZero`  | `BigDecimal`, `BigInteger`, `byte`, `short`, `int`, `long`, `double`, `float`                 | O elemento anotado deve ser um número negativo ou igual a 0.                                 |
| `@NotBlank`        | `String`, `CharSequence`                                                                      | O elemento anotado não deve ser nulo e deve conter pelo menos um caractere não em branco.    |
| `@NotEmpty`        | `String`, `Collection`, `Map`, `Array`                                                        | O elemento anotado não deve ser nulo nem vazio.                                              |
| `@NotNull`         | Qualquer tipo de objeto                                                                       | O elemento anotado não deve ser nulo.                                                        |
| `@Null`            | Qualquer tipo de objeto                                                                       | O elemento anotado deve ser nulo.                                                            |
| `@Past`            | `Date`, `Calendar`, `Instant`, `LocalDate`, `LocalDateTime`, `ZonedDateTime`                  | O elemento anotado deve ser um instante, data ou hora no passado.                            |
| `@PastOrPresent`   | `Date`, `Calendar`, `Instant`, `LocalDate`, `LocalDateTime`, `ZonedDateTime`                  | O elemento anotado deve ser um instante, data ou hora no passado ou no presente.             |
| `@Pattern`         | `String`, `CharSequence`                                                                      | A sequência de caracteres anotada deve corresponder à expressão regular especificada.        |
| `@Positive`        | `BigDecimal`, `BigInteger`, `byte`, `short`, `int`, `long`, `double`, `float`                 | O elemento anotado deve ser um número estritamente positivo.                                 |
| `@PositiveOrZero`  | `BigDecimal`, `BigInteger`, `byte`, `short`, `int`, `long`, `double`, `float`                 | O elemento anotado deve ser um número positivo ou igual a 0.                                 |
| `@Size`            | `String`, `CharSequence`, `Collection`, `Map`, `Array`                                        | O tamanho do elemento anotado deve estar entre os limites especificados (incluso).           |

> [!NOTE]
>
> Para todas as anotações mencionadas acima, existe uma variante com o sufixo `.List`. Essas variantes são usadas para definir múltiplas instâncias da mesma anotação em um único elemento. Isso é útil quando você precisa aplicar a mesma restrição com parâmetros diferentes no mesmo campo. Exemplos: `@AssertFalse.List`, `@NegativeOrZero.List` e `@Size.List`.

---

Referência: [Documentação oficial do Java](https://jakarta.ee/specifications/bean-validation/3.0/apidocs/jakarta/validation/constraints/package-summary)
