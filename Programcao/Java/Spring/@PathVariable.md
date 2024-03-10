#java #spring 
`@PathVariable` é uma anotação do Spring Framework que é usada em métodos de controladores (Controllers) para indicar que um parâmetro de método deve ser vinculado a um valor de um template de URL. Em outras palavras, ele é usado para extrair variáveis de caminho (path variables) de uma URL em uma solicitação HTTP e passá-las para o método do controlador.

Quando uma solicitação é feita para um endpoint em uma aplicação Spring Boot, o Spring MVC (Model-View-Controller) analisa a URL da solicitação e mapeia os valores dos parâmetros de caminho (path parameters) para os parâmetros de método no controlador correspondente.

Por exemplo, considere a seguinte URL: `/exemplo/123`. Neste caso, `123` é um parâmetro de caminho que está sendo passado para o endpoint `/exemplo/`. Se você estiver desenvolvendo um controlador no Spring Boot para lidar com solicitações para este endpoint, você pode usar `@PathVariable` para capturar o valor `123` e usá-lo em seu método.

Aqui está um exemplo de como você pode usar `@PathVariable` em um método de controlador Spring Boot

```java
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class ExemploController {

    @GetMapping("/exemplo/{id}")
    public String obterExemplo(@PathVariable Long id) {
        return "Exemplo com ID " + id;
    }
}
```
