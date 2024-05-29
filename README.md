<h1 align="center">
Transactions REST API Node.js
<br>
<br>
</h1>

<div align="right">
    Clique <a href="https://github.com/luc-ribeiro/transactions-api-node/blob/main/README-PTBR.md">aqui</a> para ver a versão em Português.
</div>
<br>

## 💻 Project
This project was created during the Node.js course by Rocketseat.

The project involves creating a REST API using technologies such as <strong>Fastify, Knex.js, and Vitest</strong>. The objective is to practice building APIs using these technologies and emphasize the importance of <strong>automated testing</strong>.

## 🚀 Technologies

- **Node.js** 
- **TypeScript**
- **Fastify**
- **Knex.js**
- **Vitest**
- **Zod**
- **SQLite3**

## Endpoints

#### Creating a new transaction

<details>
 <summary><code>POST</code> <code><b>/transactions</b></code> <code>(creates a new transaction)</code></summary>

##### Body

> | name      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
> | title     |  required | string                  | Transaction name                                                     |
> | amount    |  required | int                     | Transaction amount                                                    |
> | type      |  required | string                  | Transaction type ("credit" or "debit")                               |

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `201`         | `text/plain;charset=UTF-8`        | `Transaction created successfully`                                  |
> | `400`         | `application/json`                | `{"code":"400","message":"Bad Request"}`                            |
> | `405`         | `text/html;charset=utf-8`         | None                                                                |

##### cURL Example

> ```javascript
>  curl -X POST -H "Content-Type: application/json" --data @post.json http://localhost:3333/transactions
> ```

</details>

### For the endpoints below, you need to create a new transaction to generate an authentication cookie that will be stored on the device.

#### Listing transactions

<details>
 <summary><code>GET</code> <code><b>/transactions</b></code> <code>(returns all transactions)</code></summary>

##### Parameters

None.

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | JSON containing all transactions                                   |

##### cURL Example

> ```javascript
>  curl -X GET -H "Content-Type: application/json" http://localhost:3333/transactions
> ```

</details>

#### Displaying a transaction

<details>
 <summary><code>GET</code> <code><b>/transactions/{id}</b></code> <code>(displays a transaction)</code></summary>

##### Parameters

> | name      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
> | id        |  required | int                     | Unique identifier of the transaction                                  |

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | JSON containing the specific transaction                          |

##### cURL Example

> ```javascript
>  curl -X GET -H "Content-Type: application/json" http://localhost:3333/transactions/id
> ```

</details>

#### Displaying transaction summary (balance)

<details>
 <summary><code>GET</code> <code><b>/transactions/summary</b></code> <code>(displays a summary of transactions)</code></summary>

##### Parameters

None.

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | JSON containing an object with the transaction summary               |

##### cURL Example

> ```javascript
>  curl -X GET -H "Content-Type: application/json" http://localhost:3333/transactions/summary
> ```

</details>

<br>

## :page_facing_up: How to Use

- Clone this repository:

```sh
  $ git clone https://github.com/luc-ribeiro/rest-api-node.git
```

- Install the dependencies:

```sh
  # with npm
  $ npm install

  # with yarn
  $ yarn install
```

- Create a ```.env``` file following the structure of ```.env.example```

- Run the migrations:

```sh
  # with npm
  $ npm run knex migrate:latest

  # with yarn
  $ yarn knex migrate:latest
```

- Run the project:

```sh
  # with npm
  $ npm run dev

  # with yarn
  $ yarn dev
```

- The project will run on `localhost:3333`
