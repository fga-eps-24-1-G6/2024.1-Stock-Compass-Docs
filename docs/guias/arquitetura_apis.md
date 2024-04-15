# Arquitetura em Camadas para APIs RESTful: Um Mergulho Profundo

O documento a seguir tem como função explicar e exemplificar como contribuir de forma correta com microserviços do projeto Stock Compass seguindo a Aquitetura em Camadas.

A Arquitetura em Camadas é uma abordagem fundamental para construir APIs RESTful bem estruturadas e fáceis de manter. Ela separa a API em camadas distintas, cada uma com uma responsabilidade específica. Isso promove modularidade, acoplamento fraco e facilita o desenvolvimento.

#### **Camadas:**

1. **Camada de apresentação (API Layer):**
    - Trata das requisições e respostas HTTP recebidas.
    - Analisa o corpo da requisição (por exemplo, JSON) e valida a entrada do usuário.
    - Interage com a Camada de lógica de negócios para processar requisições.
    - Formata os dados para a resposta (por exemplo, converte para JSON).
2. **Camada de lógica de negócios (Service Layer):**
    - Encapsula a lógica de negócios principal da aplicação.
    - Implementa funcionalidades específicas do domínio (por exemplo, gerenciamento de usuários, processamento de pedidos).
    - Interage com a Camada de acesso a dados para recuperar e manipular dados.
    - Pode lidar com operações complexas orchestrando chamadas para múltiplos recursos.
3. **Camada de acesso a dados (Repository Layer):**
    - Camada abstrata responsável por interagir com a fonte de dados (por exemplo, banco de dados).
    - Fornece métodos para operações CRUD (Criar, Ler, Atualizar, Deletar) em dados.
    - Pode lidar com conexões, pools e mapeamento de dados para objetos de domínio.


**DTO's (Data Transfer Objects)**

DTOs são classes auxiliares que definem a estrutura dos dados que serão transferidos. Eles são particularmente úteis para evitar a exposição de entidades complexas para a camada de controller, protegendo o modelo e encapsulando lógica de validação específica.

> Dica do Batista:
>
> Pense em DTOs como a estrutura das requests e responses que iremos receber em cada endpoint. Se pergunte: "o que eu quero passar no JSON da response e o que quero receber no JSON da request??"
>
> *Por que usamos DTO's?* <br>
> Imagine por exemplo, que quando fazemos um `getUser()` não seria legal retornar toda a model `User` pois ela pode conter dados sensíveis. Ao invés disso, definimos um `GetUserDTO` e especificamos nele quais dados queremos passar adiante

#### **Benefícios:**

- **Modularidade:** Cada camada possui uma finalidade bem definida, promovendo desenvolvimento e testes independentes.
- **Manutenabilidade:** Mudanças em uma camada têm menos probabilidade de impactar outras, facilitando atualizações.
- **Reusabilidade:** Componentes de lógica de negócios podem ser reutilizados em diferentes APIs.
- **Separação de preocupações:** Separação clara entre acesso a dados e lógica da aplicação.

#### **Implementação:**

Os detalhes específicos de implementação irão variar dependendo da linguagem de programação e framework escolhidos. No entanto, algumas abordagens comuns incluem:

- Utilizar pastas ou pacotes separados para organizar o código de cada camada.
- Definir interfaces para cada camada para impor contratos e promover acoplamento fraco.
- Empregar injeção de dependência para gerenciar dependências entre camadas.

#### **Exemplo:**

Imagine uma API de e-commerce simples. A Camada de apresentação lida com requisições de usuários para informações de produtos. Ela pode chamar a Camada de lógica de negócios para recuperar detalhes do produto da Camada de acesso a dados, que interage com o banco de dados de produtos. Por fim, a Camada de apresentação formata os dados da resposta e os envia de volta ao usuário.

**Folder Structure:**

```
api/
├── controllers  // Presentation Layer
│   └── ProductController.java
├── services     // Business Logic Layer
│   └── ProductService.java
└── repositories // Data Access Layer
│   └── ProductRepository.java
└── dtos
    └── inputs
    │   └── CreateProductDTO.java
    └── outputs
        └── CreateProductDTO.java
```

**Product (Domain Model):**

```
// (This can be in a separate file or within repositories)
public class Product {
  private long id;
  private String name;
  private double price;
  // Getters and setters omitted for brevity
}
```

**ProductRepository (Data Access Layer):**

```
package api.repositories;

public interface ProductRepository {
  Product findById(long id);
  // Add methods for other CRUD operations (Create, Update, Delete)
}
```

> Dica do Batista:
>
> Quando se trata de repositórios, nós os implementamos como interfaces e usamos essas interfaces nas camadas acima (service). Aí, nós criamos uma segunda classe (`ProductRepositoryImpl`) que irá implementar a interface e irá de fato conter as queries com o banco de dados. Dessa forma caso for vantajoso mudar o banco de dados depois, só precisamos escrever outra classe de implementação, sem mexer no repositório ou nas outras camadas : )

**ProductService (Business Logic Layer):**

```
package api.services;

import api.repositories.ProductRepository;

public class ProductService {

  private final ProductRepository productRepository;

  public ProductService(ProductRepository productRepository) {
    this.productRepository = productRepository;
  }

  public Product getProductById(long id) {
    return productRepository.findById(id);
  }
  // Add methods for other business logic related to products
}
```

**ProductController (Presentation Layer):**

```
package api.controllers;

import api.services.ProductService;

import javax.ws.rs.GET;
import javax.ws.rs.Path;
import javax.ws.rs.PathParam;
import javax.ws.rs.Produces;
import javax.ws.rs.core.MediaType;

@Path("/products")
public class ProductController {

  private final ProductService productService;

  public ProductController(ProductService productService) {
    this.productService = productService;
  }

  @GET
  @Path("/{id}")
  @Produces(MediaType.APPLICATION_JSON)
  public Product getProductById(@PathParam("id") long id) {
    return productService.getProductById(id);
  }
  // Add methods for other API endpoints related to products
}
```

**DTOs (Data Transfer Objects):**

```
(request DTO)
public class CreateProductDTO {
  private String name;
  private double price;
}

(response DTO)
public class CreateProductDTO {
  private long id;
  private String name;
  private double price;
}
```

**Explicação**:

Este exemplo utiliza uma estrutura de pastas simples para separar as responsabilidades.
- A classe `Product` representa o modelo de domínio.
- A classe `ProductRepository` define uma interface para acesso a dados.
- A classe `ProductService` implementa a lógica de negócios relacionada a produtos.
- A classe `ProductController` lida com requisições HTTP recebidas e interage com o `ProductService`.
- Injeção de dependência é usada para conectar camadas (por exemplo, o construtor de `ProductService` injeta `ProductRepository`).
- O `inputs/CreateProductDTO` representa a estrutura da request no endpoint de criação de produto e `outputs/CreateProductDTO` representa a estrutura da response que iremos retornar nesse endpoint

Ao separar essas responsabilidades, você cria uma estrutura de API limpa e fácil de manter que pode crescer e se adaptar conforme sua aplicação evolui.