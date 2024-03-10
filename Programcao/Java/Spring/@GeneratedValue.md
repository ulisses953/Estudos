#java #spring 
O `@GeneratedValue` é uma anotação do Spring Framework, frequentemente utilizada em conjunto com a anotação `@Id` para especificar como os valores das chaves primárias de entidades são gerados. Essa anotação é comumente usada em entidades JPA (Java Persistence API) para mapear objetos Java para tabelas de banco de dados relacionais.

Ao usar o `@GeneratedValue`, você está indicando ao provedor JPA (como o Hibernate, por exemplo) como gerar valores para a chave primária automaticamente. Essa anotação pode ser aplicada a campos de atributos de entidades que representam chaves primárias.

Existem diferentes estratégias disponíveis para a geração de valores de chave primária, e você pode especificar qual estratégia deseja utilizar como argumento da anotação `@GeneratedValue`. Algumas das estratégias mais comuns incluem:

**AUTO:** Deixa o provedor JPA escolher automaticamente a estratégia de geração de chave primária adequada. O Hibernate, por exemplo, escolherá entre `IDENTITY`, `SEQUENCE`, e `TABLE` dependendo do banco de dados.
```java
@Id
@GeneratedValue(strategy = GenerationType.AUTO)
private Long id;

```

**IDENTITY:** Usa a capacidade de auto incremento do banco de dados para gerar valores únicos para a chave primária.
```Java
@Id
@GeneratedValue(strategy = GenerationType.IDENTITY)
private Long id;
```
**SEQUENCE:** Usa um objeto de sequência no banco de dados para gerar valores únicos para a chave primária.
```java
@Id
@GeneratedValue(strategy = GenerationType.SEQUENCE)
private Long id;
```
**TABLE:** Usa uma tabela no banco de dados para armazenar e gerenciar os valores da chave primária.
```java
@Id
@GeneratedValue(strategy = GenerationType.TABLE)
private Long id;
```