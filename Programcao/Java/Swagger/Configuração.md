#java #spring #swagger
Crie uma classe de configuração para o Swagger. Esta classe geralmente é anotada com `@Configuration` e `@EnableSwagger2` (se estiver usando a versão 2 do Swagger). No entanto, se estiver usando o Springfox 3.x, não será necessário `@EnableSwagger2`, pois ele é substituído por `@EnableOpenApi`.

```java
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import springfox.documentation.builders.PathSelectors;
import springfox.documentation.builders.RequestHandlerSelectors;
import springfox.documentation.spi.DocumentationType;
import springfox.documentation.spring.web.plugins.Docket;
import springfox.documentation.swagger2.annotations.EnableSwagger2;

@Configuration
@EnableSwagger2 // Ou @EnableOpenApi para Springfox 3.x
public class SwaggerConfig {  
    @Bean
    public Docket api() { 
        return new Docket(DocumentationType.SWAGGER_2)  
          .select()                                  
          .apis(RequestHandlerSelectors.basePackage("seu.pacote.controller"))              
          .paths(PathSelectors.any())                          
          .build();                                           
    }
}
```
Isso configura o Swagger para documentar todos os endpoints encontrados no pacote especificado (`seu.pacote.controller`).

Por padrão, a interface do Swagger estará disponível em `/swagger-ui.html` após iniciar sua aplicação Spring Boot.