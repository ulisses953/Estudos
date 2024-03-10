#java #spring 
`@PutMapping` é uma anotação usada para mapear solicitações HTTP PUT para métodos de manipulação de recursos em uma aplicação web.

Quando você desenvolve uma aplicação Spring Boot, você geralmente define métodos em classes de controladores (Controllers) para lidar com diferentes solicitações HTTP. Por exemplo, você pode ter um método em um controlador que é responsável por criar ou atualizar um recurso específico.

A anotação `@PutMapping` é usada para mapear uma solicitação HTTP PUT para um método específico em um controlador. Isso significa que quando um cliente envia uma solicitação PUT para um determinado endpoint em sua aplicação Spring Boot, o método correspondente decorado com `@PutMapping` será invocado para processar essa solicitação.

Aqui está um exemplo simples de como você pode usar `@PutMapping` em um controlador Spring Boot:

```java
import org.springframework.web.bind.annotation.PutMapping;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class ExemploController {

    @PutMapping("/exemplo/{id}")
    public String atualizarExemplo(@PathVariable Long id, @RequestBody String novoConteudo) {
        // Lógica para atualizar o recurso com o ID fornecido
        return "Recurso com ID " + id + " atualizado com sucesso com o conteúdo: " + novoConteudo;
    }
}
```
 
