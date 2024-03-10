#java #spring 
A anotação `@ExceptionHandler` é usada em métodos de controladores (Controllers) do Spring Framework para lidar com exceções lançadas durante o processamento de solicitações HTTP. Quando uma exceção ocorre em um método de um controlador, o Spring MVC procura por métodos anotados com `@ExceptionHandler` para lidar com essa exceção específica.

A principal finalidade do `@ExceptionHandler` é permitir que você centralize o tratamento de exceções em seu código, fornecendo uma maneira consistente de lidar com erros em toda a aplicação. Isso ajuda a manter um comportamento consistente em relação ao tratamento de exceções e a fornecer respostas adequadas para os clientes.

Por exemplo, considere um método de um controlador que lança uma exceção `NotFoundException` quando um recurso específico não é encontrado:

```java
import org.springframework.http.HttpStatus;
import org.springframework.web.bind.annotation.ExceptionHandler;
import org.springframework.web.bind.annotation.ResponseStatus;
import org.springframework.web.bind.annotation.RestController;
import org.springframework.web.bind.annotation.GetMapping;

@RestController
public class ExemploController {

    @GetMapping("/recurso")
    public String obterRecurso() {
        // Lógica para obter o recurso
        throw new NotFoundException("Recurso não encontrado");
    }

    @ExceptionHandler(NotFoundException.class)
    @ResponseStatus(HttpStatus.NOT_FOUND)
    public String handleNotFoundException(NotFoundException ex) {
        return ex.getMessage();
    }
}
```
Neste exemplo:

- O método `obterRecurso` é responsável por buscar um recurso. Se o recurso não for encontrado, ele lança uma exceção `NotFoundException`.
- O método `handleNotFoundException` é anotado com `@ExceptionHandler(NotFoundException.class)`. Isso indica que este método será chamado para lidar com qualquer exceção do tipo `NotFoundException` lançada por qualquer método neste controlador ou em qualquer controlador aninhado.
- O método `handleNotFoundException` retorna uma mensagem de erro com base na exceção lançada. Além disso, ele é anotado com `@ResponseStatus(HttpStatus.NOT_FOUND)`, indicando que ele retornará uma resposta com o status HTTP 404 (Not Found) para o cliente.

Essa abordagem permite que você defina facilmente como lidar com exceções específicas em sua aplicação, centralizando o tratamento de erros em métodos dedicados e mantendo um código mais limpo e organizado.

### Informações adicionais 
[[@ResponseStatus]]
[[@RestController]]

