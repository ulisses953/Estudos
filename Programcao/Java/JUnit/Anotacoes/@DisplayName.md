Utilizado para mudar o nome do método na hora da execução dos teste :

```Java
@Test
@DisplayName("Example Test Method with No Business Logic")
void test() {
	assertTrue(3 > 0);
}
```