🛒 Web Service REST API — Spring Boot + JPA/Hibernate
API REST desenvolvida como exercício prático de Web Services com Spring Boot, utilizando JPA/Hibernate para persistência e H2 Database (em memória) para ambiente de desenvolvimento e testes.

Projeto baseado nos estudos do curso "Java COMPLETO — Programação Orientada a Objetos + Projetos" (Nélio Alves – Udemy).


🚀 Tecnologias utilizadas
TecnologiaVersãoJava21Spring Boot3.xSpring Web (REST)—Spring Data JPA—Hibernate—H2 Database—Maven—

📦 Estrutura do projeto
src/main/java/
├── entities/       # Entidades JPA (mapeamento das tabelas)
├── repositories/   # Interfaces JpaRepository
├── services/       # Regras de negócio / camada de serviço
└── resources/      # Controllers REST (endpoints)

🗄️ Modelo de dados (H2)
Tabelas geradas automaticamente via JPA/Hibernate:

TB_USER
TB_ORDER
TB_ORDER_ITEM
TB_PAYMENT
TB_PRODUCT
TB_CATEGORY
TB_PRODUCT_CATEGORY


🔗 Endpoints
Base URL: http://localhost:8080

⚠️ A API atual implementa apenas operações de leitura (GET). Operações de escrita (POST, PUT, DELETE) estão previstas como evolução futura.

Users
MétodoEndpointDescriçãoStatusGET/usersLista todos os usuários200GET/users/{id}Busca usuário por ID200 / 404
Exemplo de resposta — GET /users/1:
json{
  "id": 1,
  "name": "Maria Brown",
  "email": "maria@gmail.com",
  "phone": "988888888"
}

Orders
MétodoEndpointDescriçãoStatusGET/ordersLista todos os pedidos200GET/orders/{id}Busca pedido por ID200 / 404
Exemplo de resposta — GET /orders/1:
json{
  "id": 1,
  "moment": "2019-06-20T19:53:07Z",
  "orderStatus": "PAID",
  "client": {
    "id": 1,
    "name": "Maria Brown"
  },
  "items": [
    {
      "quantity": 2,
      "price": 90.5,
      "subTotal": 181.0,
      "product": {
        "id": 1,
        "name": "The Lord of the Rings"
      }
    }
  ],
  "total": 181.0
}

Products
MétodoEndpointDescriçãoStatusGET/productsLista todos os produtos200GET/products/{id}Busca produto por ID200 / 404
Exemplo de resposta — GET /products/1:
json{
  "id": 1,
  "name": "The Lord of the Rings",
  "description": "Lorem ipsum dolor sit amet",
  "price": 90.5,
  "imgUrl": "",
  "categories": [
    { "id": 2, "name": "Books" }
  ]
}

Categories
MétodoEndpointDescriçãoStatusGET/categoriesLista todas as categorias200GET/categories/{id}Busca categoria por ID200 / 404
Exemplo de resposta — GET /categories/1:
json{
  "id": 1,
  "name": "Electronics"
}

▶️ Como executar
Pré-requisitos

JDK 21 instalado e configurado
Eclipse com Spring Tools Suite (STS) ou IntelliJ IDEA
Maven (ou Maven Wrapper incluso no projeto)

Passo a passo
bash# 1. Clone o repositório
git clone https://github.com/PedroMenezes296/springboot-jpa-rest

# 2. Importe no Eclipse/STS:
# File > Import > Existing Maven Projects
# Aguarde o Maven baixar as dependências

# 3. Execute:
# Botão direito no projeto > Run As > Spring Boot App
O console indicará o Tomcat rodando em http://localhost:8080.

🗃️ H2 Console
Com a aplicação rodando, acesse o banco em memória:
URL: http://localhost:8080/h2-console
Driver Class: org.h2.Driver
JDBC URL:     jdbc:h2:mem:testdb
User Name:    sa
Password:     (vazio)

🧪 Testando com Postman
Importe as requisições abaixo ou teste diretamente no browser/Postman:
GET http://localhost:8080/users
GET http://localhost:8080/users/1
GET http://localhost:8080/orders
GET http://localhost:8080/orders/1
GET http://localhost:8080/products
GET http://localhost:8080/products/1
GET http://localhost:8080/categories
GET http://localhost:8080/categories/1

🧠 O que foi praticado

Construção de API REST com Spring Boot
Modelagem de entidades e relacionamentos JPA: @OneToMany, @ManyToOne, @OneToOne, tabelas de associação
Persistência com Hibernate
H2 em memória para desenvolvimento e testes
Testes de endpoints com Postman
Organização em camadas: Resource → Service → Repository


🔮 Próximos passos

 Implementar operações de escrita (POST, PUT, DELETE)
 Adicionar DTOs para controlar o JSON retornado
 Implementar tratamento de erros com @ControllerAdvice
 Adicionar validações com spring-boot-starter-validation
 Documentar a API com Swagger/OpenAPI
 Criar profiles dev e prod (ex.: PostgreSQL em produção)


👤 Autor
Pedro Menezes
github.com/PedroMenezes296
