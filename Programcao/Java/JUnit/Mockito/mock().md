
**Criação de Mocks:** O método `mock()` é utilizado para criar instâncias de mocks. Esses mocks são objetos simulados que se comportam como as classes ou interfaces que estão sendo simuladas, mas permitem que você defina comportamentos específicos para métodos e verifique chamadas.

Exemplo de criação de um mock de uma interface em Java:

```Java
// Criação de um mock para uma interface 
MyInterface myMock = Mockito.mock(MyInterface.class);
```

Exemplo de criação de um mock de uma classe concreta:

```java
// Criação de um mock para uma classe concreta
MyClass myMock = Mockito.mock(MyClass.class);
```