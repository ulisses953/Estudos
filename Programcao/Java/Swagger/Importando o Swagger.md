#java #spring #swagger 
Para importar o Swagger no seu projeto Spring Boot, você precisa adicionar as dependências corretas ao seu arquivo `pom.xml` (se estiver usando Maven) ou `build.gradle` (se estiver usando Gradle). Aqui estão as dependências necessárias para integrar o Swagger com o Spring Boot:

Se estiver utilizando Maven, adicione o seguinte ao seu arquivo `pom.xml` dentro da seção `<dependencies>`:

xml

```XML
<!-- Swagger -->
<dependency>
    <groupId>io.springfox</groupId>
    <artifactId>springfox-swagger2</artifactId>
    <version>3.0.0</version> <!-- Verifique a versão mais recente -->
</dependency>
<dependency>
    <groupId>io.springfox</groupId>
    <artifactId>springfox-swagger-ui</artifactId>
    <version>3.0.0</version> <!-- Verifique a versão mais recente -->
</dependency>

```

Se estiver utilizando Gradle, adicione o seguinte ao seu arquivo `build.gradle` dentro da seção `dependencies`:

groovy

```groovy
// Swagger
implementation 'io.springfox:springfox-swagger2:3.0.0' // Verifique a versão mais recente
implementation 'io.springfox:springfox-swagger-ui:3.0.0' // Verifique a versão mais recente

```


