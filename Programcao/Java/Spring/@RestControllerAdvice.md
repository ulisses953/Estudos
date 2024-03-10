`@RestControllerAdvice` é uma anotação do Spring Framework que combina as funcionalidades de `@ControllerAdvice` e `@ResponseBody`. Ela é usada para criar classes globais que tratam exceções em toda a aplicação Spring Boot e retornam respostas HTTP diretamente no corpo da resposta, sem a necessidade de uma visualização (view).

Quando você anota uma classe com `@RestControllerAdvice`, ela atua como um controlador global que pode conter métodos anotados com `@ExceptionHandler`, `@InitBinder` e `@ModelAttribute`, semelhante ao que você faria em um controlador tradicional.

Aqui está um exemplo de como você pode usar `@RestControllerAdvice` para lidar com exceções em toda a sua aplicação:

```java
mport org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.ExceptionHandler;
import org.springframework.web.bind.annotation.RestControllerAdvice;

@RestControllerAdvice
public class GlobalExceptionHandler {

    @ExceptionHandler(Exception.class)
    public ResponseEntity<String> handleException(Exception ex) {
        return ResponseEntity.status(HttpStatus.INTERNAL_SERVER_ERROR).body("Ocorreu um erro interno: " + ex.getMessage());
    }

    @ExceptionHandler(NotFoundException.class)
    public ResponseEntity<String> handleNotFoundException(NotFoundException ex) {
        return ResponseEntity.status(HttpStatus.NOT_FOUND).body("Recurso não encontrado: " + ex.getMessage());
    }
}
```

Neste exemplo:

- A classe `GlobalExceptionHandler` é anotada com `@RestControllerAdvice`, indicando que ela é responsável por lidar com exceções em toda a aplicação.
- Existem dois métodos anotados com `@ExceptionHandler`. O primeiro método trata exceções genéricas `Exception`, retornando um status HTTP 500 (Internal Server Error) com uma mensagem de erro adequada. O segundo método trata exceções específicas `NotFoundException`, retornando um status HTTP 404 (Not Found) com uma mensagem de erro adequada.
- Ambos os métodos retornam um objeto `ResponseEntity<String>`, que permite definir o status HTTP e o corpo da resposta diretamente.

### Informações adicionais 

[[@ExceptionHandler]] 