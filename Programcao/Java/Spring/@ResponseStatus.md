#java #spring 
A anotação `@ResponseStatus` é usada em métodos de controladores (Controllers) do Spring Framework para definir o código de status HTTP que será retornado quando o método for invocado com sucesso. Ele permite que você especifique o código de status HTTP que deseja que seja retornado para o cliente em uma resposta bem-sucedida.

Por exemplo, se você deseja que um método de um controlador retorne um código de status HTTP 200 (OK) em vez do padrão, você pode usar `@ResponseStatus` para especificar isso. Veja um exemplo:

```java
import org.springframework.web.bind.annotation.ResponseStatus;
import org.springframework.http.HttpStatus;
import org.springframework.web.bind.annotation.RestController;
import org.springframework.web.bind.annotation.GetMapping;

@RestController
public class ExemploController {

    @GetMapping("/status")
    @ResponseStatus(HttpStatus.OK)
    public String obterStatus() {
        return "Serviço está funcionando corretamente";
    }
}
```

Neste exemplo, o método `obterStatus` retorna uma mensagem simples indicando que o serviço está funcionando corretamente. Por padrão, o status HTTP retornado seria 200 (OK) neste caso. No entanto, a anotação `@ResponseStatus(HttpStatus.OK)` é usada para explicitamente definir o código de status HTTP como 200.

Você também pode usar `@ResponseStatus` para mapear métodos de controladores para outros códigos de status HTTP, como 404 (Not Found), 500 (Internal Server Error), etc. Isso permite que você forneça respostas adequadas aos clientes com base na lógica de negócios da sua aplicação.

### Informações adicionais 

[[@GetMapping]]
[[@ResponseStatus]]