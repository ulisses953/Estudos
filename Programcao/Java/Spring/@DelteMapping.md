#java #spring

A anotação `@DeleteMapping` é usada no Spring Framework para mapear solicitações HTTP DELETE para métodos específicos em um controlador (Controller) de uma aplicação Spring Boot.

Quando você está desenvolvendo uma aplicação Spring Boot e precisa criar um endpoint para deletar recursos, você pode usar a anotação `@DeleteMapping` para mapear esse comportamento. Esta anotação indica que um determinado método em um controlador será invocado quando uma solicitação HTTP DELETE for feita para um determinado endpoint.

Aqui está um exemplo de como você pode usar `@DeleteMapping`:

```java
mport org.springframework.web.bind.annotation.DeleteMapping;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class ExemploController {

    @DeleteMapping("/exemplo/{id}")
    public String deletarExemplo(@PathVariable Long id) {
        // Lógica para deletar o recurso com o ID fornecido
        return "Recurso com ID " + id + " deletado com sucesso";
    }
}
```

### Informações adicionais 

[[@RestController]]
