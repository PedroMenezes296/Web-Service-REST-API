# Projeto Web Service com Spring Boot + JPA/Hibernate (H2)

API REST desenvolvida como exercício prático de **Web Services com Spring Boot**, utilizando **JPA/Hibernate** para persistência e **H2 Database (em memória)** para ambiente de testes/desenvolvimento.

> Projeto baseado em estudos do curso **“Java COMPLETO Programação Orientada a Objetos + Projetos” (Nélio Alves – Udemy)**.

---

## Tecnologias utilizadas

- **Java 21**
- **Spring Boot**
- **Spring Web (REST)**
- **Spring Data JPA**
- **Hibernate**
- **H2 Database**
- **Maven**
- **Postman** (para testes de endpoints)

---

## Visão geral do banco (H2)

Tabelas principais (geradas via JPA/Hibernate):

- `TB_USER`
- `TB_ORDER`
- `TB_ORDER_ITEM`
- `TB_PAYMENT`
- `TB_PRODUCT`
- `TB_CATEGORY`
- `TB_PRODUCT_CATEGORY`

---

## Endpoints disponíveis

Base URL:
- `http://localhost:8080`

### Users
- `GET /users`
- `GET /users/{id}`

### Orders
- `GET /orders`
- `GET /orders/{id}`

### Products
- `GET /products`
- `GET /products/{id}`

### Categories
- `GET /categories`
- `GET /categories/{id}`

> Obs.: Os endpoints podem variar conforme sua implementação (controllers). A lista acima segue o padrão do projeto.

---

## Como executar o projeto (Eclipse / Spring Tools)

### Pré-requisitos
- **JDK 21** instalado e configurado
- **Spring Tools for Eclipse** (ou Eclipse com plugins do Spring)
- **Maven** (geralmente já funciona via Maven Wrapper se existir no projeto)

### Passo a passo
1. Clone o repositório:
   ```bash
   git clone https://github.com/PedroMenezes296/demo-dao-JDBC

Importe o projeto no Eclipse/STS:

File > Import > Existing Maven Projects

Aguarde o Maven baixar as dependências.

Execute:

Clique com o botão direito no projeto

Run As > Spring Boot App

Quando subir, o console vai indicar o Tomcat rodando na porta 8080.

Acessando o H2 Console

Com a aplicação rodando, acesse:

http://localhost:8080/h2-console

Configuração típica (pode variar conforme application.properties):

Driver Class: org.h2.Driver

JDBC URL: jdbc:h2:mem:testdb

User Name: sa

Password: (vazio)

Testando via Postman

Exemplos de requisições:

GET http://localhost:8080/users

GET http://localhost:8080/users/1

GET http://localhost:8080/orders

GET http://localhost:8080/orders/1

Estrutura do projeto (alto nível)

Padrão comum em projetos Spring Boot com JPA:

entities → Entidades JPA (mapeamento das tabelas)

repositories → Interfaces JpaRepository

services → Regras de negócio / camada de serviço

resources → Controllers REST (endpoints)

O que eu pratiquei com esse projeto

Construção de uma API REST com Spring Boot

Modelagem de entidades e relacionamentos JPA:

@OneToMany, @ManyToOne, @OneToOne, tabelas de associação

Persistência com Hibernate

Uso do H2 em memória para desenvolvimento/testes

Testes de endpoints com Postman

Organização em camadas: Resource → Service → Repository

Próximos passos (ideias de evolução)

Adicionar validações com spring-boot-starter-validation

Documentar a API com Swagger/OpenAPI

Implementar DTOs para controlar melhor o JSON retornado

Adicionar tratamento de erros com @ControllerAdvice

Criar profile dev e prod (ex.: PostgreSQL)

Repositório
https://github.com/PedroMenezes296/demo-dao-JDBC

Autor
Pedro Menezes
