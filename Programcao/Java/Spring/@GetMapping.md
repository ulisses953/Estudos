#java #spring 
`@GetMapping` é uma anotação do Spring Framework usada em métodos de controladores (Controllers) para mapear solicitações HTTP GET para métodos específicos. Essa anotação é uma forma conveniente de mapear endpoints da API REST a métodos em classes de controladores em uma aplicação Spring Boot.

Quando você marca um método com `@GetMapping`, o Spring Boot configura automaticamente esse método para responder a solicitações HTTP GET para o endpoint especificado.

Aqui está um exemplo de como você pode usar `@GetMapping`:

```java
import org.springframework.web.bind.annotation.RestController;
import org.springframework.web.bind.annotation.GetMapping;

@RestController
public class ExemploController {

    @GetMapping("/exemplo")
    public String exemplo() {
        return "Esta é uma resposta da API REST!";
    }
}
```

Neste exemplo, a anotação `@GetMapping("/exemplo")` é usada para mapear o método `exemplo()` para o endpoint `/exemplo`. Quando uma solicitação HTTP GET é feita para `/exemplo`, o método `exemplo()` será chamado e retornará uma string "Esta é uma resposta da API REST!". O Spring Boot automaticamente converte essa string em uma resposta HTTP, que é enviada de volta ao cliente.

`@GetMapping` é uma maneira conveniente de configurar endpoints de API REST em uma aplicação Spring Boot, fornecendo uma abordagem simples e declarativa para definir a correspondência entre endpoints e métodos em controladores.

### Informações adicionais 

[[@RestController]]