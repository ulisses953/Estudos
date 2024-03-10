#java #spring 
As consultas por método são uma abordagem conveniente e eficaz fornecida pelo Spring Data para criar consultas de banco de dados com base nos nomes dos métodos definidos em interfaces de repositório. Isso elimina a necessidade de escrever consultas SQL manualmente, tornando o desenvolvimento de acesso a dados mais fácil e menos propenso a erros.

A ideia por trás das consultas por método é que o Spring Data interpreta o nome dos métodos do repositório para criar consultas SQL correspondentes. Ele segue uma convenção de nomenclatura específica para analisar os nomes dos métodos e gerar as consultas apropriadas.

## Convenções básicas:

- Comece o nome do método com um prefixo que indique a ação desejada, como `findBy`, `findAllBy`, `getBy`, etc.
- Use o nome das propriedades da entidade para filtrar os resultados. O Spring Data irá mapear automaticamente esses nomes para os campos correspondentes no banco de dados 
## Palavras-chave reservadas

|   Palavra-chave    |                          Exemplo                          |                          JPQL snippet                          |
| :----------------: | :-------------------------------------------------------: | :------------------------------------------------------------: |
|      Distinct      |            findDistinctByLastnameAndFirstname             | select distinct …​ where x.lastname = ?1 and x.firstname = ?2  |
|        And         |                findByLastnameAndFirstname                 |          … where x.lastname = ?1 and x.firstname = ?2          |
|         Or         |                 findByLastnameOrFirstname                 |          … where x.lastname = ?1 or x.firstname = ?2           |
|     Is, Equals     | findByFirstname, findByFirstnameIs, findByFirstnameEquals |                    … where x.firstname = ?1                    |
|      Between       |                  findByStartDateBetween                   |             … where x.startDate between ?1 and ?2              |
|      LessThan      |                     findByAgeLessThan                     |                       … where x.age < ?1                       |
|   LessThanEqual    |                  findByAgeLessThanEqual                   |                      … where x.age <= ?1                       |
|    GreaterThan     |                   findByAgeGreaterThan                    |                       … where x.age > ?1                       |
|  GreaterThanEqual  |                 findByAgeGreaterThanEqual                 |                      … where x.age >= ?1                       |
|       After        |                   findByStartDateAfter                    |                    … where x.startDate > ?1                    |
|       Before       |                   findByStartDateBefore                   |                    … where x.startDate < ?1                    |
|    IsNull, Null    |                     findByAge(Is)Null                     |                     … where x.age is null                      |
| IsNotNull, NotNull |                   findByAge(Is)NotNull                    |                     … where x.age not null                     |
|        Like        |                    findByFirstnameLike                    |                  … where x.firstname like ?1                   |
|      NotLike       |                  findByFirstnameNotLike                   |                … where x.firstname not like ?1                 |
|    StartingWith    |                findByFirstnameStartingWith                | … where x.firstname like ?1 (parameter bound with appended %)  |
|     EndingWith     |                 findByFirstnameEndingWith                 | … where x.firstname like ?1 (parameter bound with prepended %) |
|     Containing     |                 findByFirstnameContaining                 |   … where x.firstname like ?1 (parameter bound wrapped in %)   |
|      OrderBy       |               findByAgeOrderByLastnameDesc                |          … where x.age = ?1 order by x.lastname desc           |
|        Not         |                     findByLastnameNot                     |                    … where x.lastname <> ?1                    |
|         In         |             findByAgeIn(Collection<Age> ages)             |                      … where x.age in ?1                       |
|       NotIn        |           findByAgeNotIn(Collection<Age> ages)            |                    … where x.age not in ?1                     |
|        True        |                    findByActiveTrue()                     |                    … where x.active = true                     |
|       False        |                    findByActiveFalse()                    |                    … where x.active = false                    |
|     IgnoreCase     |                 findByFirstnameIgnoreCase                 |             … where UPPER(x.firstname) = UPPER(?1)             |

## **Parâmetros dinâmicos**:

O Spring Data também suporta a criação de consultas com parâmetros dinâmicos. Isso significa que você pode criar consultas que aceitam parâmetros como argumentos de método e filtram os resultados com base nesses parâmetros.

Aqui está um exemplo simples de como você pode usar consultas por método no Spring Data:

Suponha que você tenha uma entidade `Produto` com campos como `nome`, `preco` e `categoria`. E você deseja buscar produtos por nome e categoria.

```java
import java.util.List;
import org.springframework.data.jpa.repository.JpaRepository;
import org.springframework.stereotype.Repository;

@Repository
public interface ProdutoRepository extends JpaRepository<Produto, Long> {
    List<Produto> findByNome(String nome);
    List<Produto> findByNomeAndCategoria(String nome, String categoria);
    List<Produto> findByPrecoGreaterThan(BigDecimal preco);
}
```

Neste exemplo:

- `findByNome` retorna uma lista de produtos com um determinado nome.
- `findByNomeAndCategoria` retorna uma lista de produtos com um determinado nome e categoria.
- `findByPrecoGreaterThan` retorna uma lista de produtos com um preço superior a um determinado valor.

O Spring Data analisa automaticamente esses nomes de método e gera consultas SQL correspondentes, permitindo que você execute operações de busca de forma simples e eficaz, sem escrever consultas SQL manualmente. Essa abordagem é altamente produtiva e facilita muito o desenvolvimento de acesso a dados em aplicativos Spring.
