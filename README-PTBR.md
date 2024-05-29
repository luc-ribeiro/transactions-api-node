<h1 align="center">
Transactions REST API Node.js
<br>
<br>
</h1>

<div align="right">
  Click <a href="https://github.com/luc-ribeiro/transactions-api-node/blob/main/README.md">here</a> to view the english version.
</div>
<br>

## 💻 Projeto
Este projeto foi criado durante o curso de Node.js da Rocketseat.

O projeto consiste na criação de uma API REST, utilizando tecnologias como <strong>Fastify, Knex.js e Vitest</strong>.
O objetivo é praticar a criação de APIs com a utilização dessas tecnologias e enfatizar a importância de <strong>testes automatizados</strong>.

## 🚀 Tecnologias

- **Node.js** 
- **TypeScript**
- **Fastify**
- **Knex.js**
- **Vitest**
- **Zod**
- **SQLite3**

## Endpoints

#### Criando uma nova transação

<details>
 <summary><code>POST</code> <code><b>/transactions</b></code> <code>(cria uma nova transação)</code></summary>

##### Corpo

> | name      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
> | title     |  required | string                  | Nome da transação                                                     |
> | amount    |  required | int                     | Valor da transação                                                    |
> | type      |  required | string                  | Tipo da transação ("credit" ou "debit")                               |

##### Respostas

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `201`         | `text/plain;charset=UTF-8`        | `Transaction created successfully`                                  |
> | `400`         | `application/json`                | `{"code":"400","message":"Bad Request"}`                            |
> | `405`         | `text/html;charset=utf-8`         | None                                                                |

##### Exemplo cURL

> ```javascript
>  curl -X POST -H "Content-Type: application/json" --data @post.json http://localhost:3333/transactions
> ```

</details>

### Para os endpoints abaixo, é necessário gerar uma nova transação, para que seja criado um cookie de autenticação e armazenado no dispositivo.

#### Listando transações

<details>
 <summary><code>GET</code> <code><b>/transactions</b></code> <code>(retorna todas as transações)</code></summary>

##### Parâmetros

Nenhum.

##### Respostas

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | JSON contendo todas as transações                                   |

##### Exemplo cURL

> ```javascript
>  curl -X GET -H "Content-Type: application/json" http://localhost:3333/transactions
> ```

</details>

#### Exibindo uma transação

<details>
 <summary><code>GET</code> <code><b>/transactions/{id}</b></code> <code>(exibe uma transação)</code></summary>

##### Parâmetros

> | name      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
> | id        |  required | int                     | Identificador único da transação                                      |

##### Respostas

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | JSON contendo a transação do ID específico                          |

##### Exemplo cURL

> ```javascript
>  curl -X GET -H "Content-Type: application/json" http://localhost:3333/transactions/id
> ```

</details>

#### Exibindo o montante das transações (saldo)

<details>
 <summary><code>GET</code> <code><b>/transactions/summary</b></code> <code>(exibe um resumo com o montante das transações)</code></summary>

##### Parâmetros

Nenhum.

##### Respostas

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | JSON contendo um objeto com o montante das transações               |

##### Exemplo cURL

> ```javascript
>  curl -X GET -H "Content-Type: application/json" http://localhost:3333/transactions/summary
> ```

</details>

<br>

## :page_facing_up: Como utilizar

- Faça um clone deste repositório:

```sh
  $ git clone https://github.com/luc-ribeiro/rest-api-node.git
```

- Instale as dependências:

```sh
  # com npm
  $ npm install

  # com yarn
  $ yarn install
```

- Crie um arquivo ```.env``` seguindo a estrutura do ```.env.example```

- Rode as migrations:

```sh
  # com npm
  $ npm run knex migrate:latest

  # com yarn
  $ yarn knex migrate:latest
```

- Execute o comando:

```sh
  # com npm
  $ npm run dev

  # com yarn
  $ yarn dev
```

- O projeto rodará em `localhost:3333`
