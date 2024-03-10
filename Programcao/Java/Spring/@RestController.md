`@RestController` é uma anotação do Spring Framework usada para marcar classes que definem controladores (Controllers) em uma aplicação Spring Boot. Essa anotação é uma combinação de duas anotações: `@Controller` e `@ResponseBody`.

Quando você usa `@RestController` em uma classe, significa que todos os métodos dessa classe serão tratados como endpoints da API REST. O Spring Boot automaticamente converte o resultado retornado por esses métodos para o formato apropriado de resposta HTTP, geralmente JSON ou XML, dependendo do cabeçalho `Accept` na solicitação.

Aqui está um exemplo de como você pode usar `@RestController`:
```java
import org.springframework.web.bind.annotation.RestController;
import org.springframework.web.bind.annotation.GetMapping;

@RestController
public class ExemploController {

    @GetMapping("/exemplo")
    public String exemplo() {
        return "Olá, mundo!";
    }
}
```

Neste exemplo, a classe `ExemploController` é marcada com `@RestController`, o que indica que esta classe é um controlador REST. O método `exemplo()` é um endpoint que responde a solicitações GET para `/exemplo`. Quando uma solicitação GET é feita para esse endpoint, o texto "Olá, mundo!" será retornado como resposta. O Spring Boot automaticamente converte esse texto em uma resposta HTTP com o corpo da resposta contendo "Olá, mundo!".

`@RestController` é uma maneira conveniente de simplificar o desenvolvimento de APIs RESTful em uma aplicação Spring Boot, pois elimina a necessidade de anotar métodos individuais com `@ResponseBody`. Em vez disso, ele aplica automaticamente a semântica de resposta adequada a todos os métodos dentro da classe marcada com `@RestController`.

### Informações adicionais 
[[@GetMapping]]