UUID (Universal Unique Identifier) ​​é um valor de 128 bits usado para identificar exclusivamente objetos ou entidades em um sistema de computador ou na Internet. UUIDs são cadeias de caracteres de 36 caracteres projetadas para serem globalmente exclusivas, minimizando a chance de dois UUIDs serem iguais, mesmo em computadores ou horários diferentes. Ele é usado para encontrar aplicativos como chaves primárias em bancos de dados, para gerar nomes de arquivos exclusivos, em sistemas de computação distribuídos, como identificadores de sessão e em vários protocolos de rede. UUIDs são persistentes, escalável, e amplamente adotados por sua confiabilidade e facilidade de implementação em sistemas que requerem identificação exclusiva.

```java
@Id
@GeneratedValue
private UUID courseId;
```
[Para mais detalhes ](https://www.baeldung.com/hibernate-identifiers)