# Authentication API

## Java Spring Postgres JWT

Este projeto é uma API construída utilizando Java, Spring Framework, Migrações Flyway, PostgreSQL como banco de dados, e Spring Security com JWT para controle de autenticação.

## Sumário

- [Instalação](#instalação)
- [Configuração](#configuração)
- [Uso](#uso)
- [Endpoints da API](#endpoints-da-api)
- [Autenticação](#autenticação)
- [Banco de Dados](#banco-de-dados)
- [Créditos](#créditos)

## Instalação

1. Clone o repositório:
    ```bash
    git clone https://github.com/seu-usuario/seu-repositorio.git
    ```

2. Instale as dependências com Maven:
    ```bash
    mvn install
    ```

3. Instale o PostgreSQL.

## Configuração

1. Configure o banco de dados PostgreSQL e ajuste as configurações de conexão no arquivo `application.properties`.

2. Execute as migrações do Flyway para preparar o banco de dados:
    ```bash
    mvn flyway:migrate
    ```

## Uso

1. Inicie a aplicação com Maven:
    ```bash
    mvn spring-boot:run
    ```

2. A API estará acessível em `http://localhost:8080`.

## Endpoints da API

A API fornece os seguintes endpoints:

- **GET /product** - Recupera a lista de todos os produtos. (todos os usuários autenticados)
- **POST /product** - Registra um novo produto. (necessário acesso ADMIN)
- **POST /auth/login** - Faz login no aplicativo.
- **POST /auth/register** - Registra um novo usuário no aplicativo.

## Autenticação

A API utiliza Spring Security para controle de autenticação. Os seguintes roles estão disponíveis:

- **USER** -> Role padrão para usuários logados.
- **ADMIN** -> Role de administrador para gerenciar parceiros (registrar novos parceiros).

Para acessar endpoints protegidos como um usuário ADMIN, forneça as credenciais de autenticação apropriadas no cabeçalho da requisição.

## Banco de Dados

O projeto utiliza PostgreSQL como banco de dados. As migrações necessárias do banco de dados são gerenciadas pelo Flyway.

## Créditos

Este projeto foi desenvolvido com base no tutorial da Fernanda Kipper. Confira o vídeo tutorial [aqui](https://www.youtube.com/watch?v=5w-YCcOjPD0&t=1s&ab_channel=FernandaKipper%7CDev).
