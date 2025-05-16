# Projeto Blog Pessoal - Backend com Spring Boot

<br />

<div align="center">
    <img src="https://i.imgur.com/w8tTOuT.png" title="source: imgur.com" /> 
</div>

<br />

<div align="center">
  <img src="https://img.shields.io/github/languages/top/feperonica/blog-pessoal?style=flat-square" />
  <img src="https://img.shields.io/github/repo-size/feperonica/blog-pessoal?style=flat-square" />
  <img src="https://img.shields.io/github/languages/count/feperonica/blog-pessoal?style=flat-square" />
  <img src="https://img.shields.io/github/last-commit/feperonica/blog-pessoal?style=flat-square" />
  <img src="https://img.shields.io/github/issues/feperonica/blog-pessoal?style=flat-square" />
  <img src="https://img.shields.io/github/issues-pr/feperonica/blog-pessoal?style=flat-square" />
  <img src="https://img.shields.io/badge/status-construção-yellow" alt="Status: Em Construção">
</div>

<br />

## 1. Descrição

O **Blog Pessoal** é uma aplicação que permite que usuários publiquem, editem e visualizem postagens relacionadas a temas variados, de forma organizada e segura. Este projeto foi desenvolvido com fins educacionais, simulando uma aplicação real de blog para praticar conceitos de API REST com Java e Spring Boot.

Entre os principais recursos que um blog pessoal oferece, destacam-se:

1. Criação, edição e exclusão de postagens
2. Associação de postagens a temas específicos
3. Cadastro e autenticação de usuários
4. Visualização de postagens por tema ou usuário
5. Controle de acesso a operações sensíveis

## 2. Sobre esta API

A API do Blog Pessoal foi desenvolvida utilizando **Java** e o **framework Spring**, seguindo os princípios da Arquitetura MVC e REST. Ela oferece endpoints para o gerenciamento dos recursos **Usuário**, **Postagem** e **Tema**, permitindo a interação entre os usuários e os conteúdos publicados.

### 2.1. Principais funcionalidades da API:

1. Consulta, cadastro, login e atualização dos dados de usuários
2. Consulta, criação e gerenciamento de temas para classificar postagens
3. Criação, edição, listagem e remoção de postagens
4. Associação de postagens a temas e autores
5. Autenticação via token JWT para segurança nas requisições

## 3. Diagrama de Classes

```mermaid
classDiagram
class Postagem {
  - id : Long
  - titulo : String
  - texto : String
  - data : LocalDateTime
  - tema : Tema
  - usuario : Usuario
}
class Tema {
  - id : Long
  - descricao : String
  - postagens : List<Postagem>
}
class Usuario {
  - id : Long
  - nome : String
  - usuario : String
  - senha : String
  - foto : String
  - postagens : List<Postagem>
}
Tema "1" --> "0..*" Postagem : classifica
Usuario "1" --> "0..*" Postagem : cria
```

## 4. Diagrama Entidade-Relacionamento (DER)

```mermaid
erDiagram
    tb_usuarios ||--o{ tb_postagens : escreve
    tb_temas ||--o{ tb_postagens : classifica
    tb_usuarios {
        bigint id PK
        varchar(255) nome
        varchar(255) usuario
        varchar(255) senha
        varchar(5000) foto
    }
    tb_temas {
        bigint id PK
        varchar(255) descricao
    }
    tb_postagens {
        bigint id PK
        varchar(255) titulo
        text texto
        datetime data
        bigint tema_id FK
        bigint usuario_id FK
    }
```

## 5. Tecnologias utilizadas

| Item                          | Descrição       |
| ----------------------------- | --------------- |
| **Servidor**                  | Tomcat          |
| **Linguagem de programação**  | Java            |
| **Framework**                 | Spring Boot     |
| **ORM**                       | JPA + Hibernate |
| **Banco de dados Relacional** | MySQL           |
| **Segurança**                 | Spring Security |
| **Autenticação**              | JWT             |
| **Testes automatizados**      | JUnit           |
| **Documentação**              | SpringDoc       |

## 6. Requisitos

Para executar os códigos localmente, você precisará:

- [Java JDK 17+](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html)
- Banco de dados [MySQL](https://dev.mysql.com/downloads/)
- [STS](https://spring.io/tools)
- [Insomnia](https://insomnia.rest/download) ou [Postman](https://www.postman.com/)

## 7. Como Executar o projeto no STS

### 7.1. Importando o Projeto

1. Clone o repositório do Projeto Blog Pessoal

```bash
git clone https://github.com/feperonica/blog-pessoal.git
```

2. Abra o STS e importe como projeto existente no workspace.

### 7.2. Executando o projeto

1. Na Guia **Boot Dashboard**, localize o **Projeto Blog Pessoal**
2. Clique no botão **Start or Restart**
3. Acompanhe a inicialização no console do STS
4. Verifique se o banco de dados `db_blogpessoal` foi criado corretamente
5. Use o Insomnia ou Postman para testar os endpoints

## 8. Contribuição

Este repositório é parte de um projeto educacional, mas contribuições são sempre bem-vindas! Caso tenha sugestões, correções ou melhorias, fique à vontade para:

- Criar uma **issue**
- Enviar um **pull request**
- Compartilhar com colegas que estejam aprendendo Java!

##  9. Contato

Desenvolvido por [**Felipe Peronica**](https://github.com/feperonica)  
📧 felipeperonica@gmail.com
