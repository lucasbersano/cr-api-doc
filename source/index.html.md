---
title: Referencia API

language_tabs:
  - javascript

# toc_footers:
#   - <a href='#'>Sign Up for a Developer Key</a>
#   - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introdução

Benvido a documentação do Atendimento Total. API é baseada no padrão Graphql, é possivel explorar utilizando graphiql em
https://apitest.crhoteisbrasil.com.br/api. Para os exemplos utilizamos a lib "graph-request".

Todas as requiçoes precisam de uma chava para pode interagir com API. As resposta são em JSON, caso não tenha expereriencia com GraphQL lei esta documentação. https://graphql.org/learn/queries/

# Autenticação

> Para qualquer query, precisa se anexado a chave.

```javascript
import { request } from "graphql-request";

const query = `{
    acomodacoesComTarifario(
      acomodacaoComTarifarioSelect: { chave: "sua-chave" }
    ) {
      maxadt
      msgadtes
    }
}`;

request("https://apitest.crhoteisbrasil.com.br/api", query).then(data =>
  console.log(data)
);
```

> Lembrese de trocar `sua-chave` para sua chave de accesso

TODO

<aside class="notice">
Lembrese de trocar  <code>sua-chave</code> para sua chave de accesso
</aside>

# Acomodações

## Listar todas as acomodações

```javascript
import { request } from "graphql-request";

const query = `{
	acomodacoes(acomodacaoSelect: {chave: "sua-chave"}) {
    nome
  }
}`;
```

> O comando de cima retornar o seguinte JSON

```json
{
  "data": {
    "acomodacoes": [
      {
        "nome": "Ap 3 quartos - Ate 9 pessoas"
      },
      {
        "nome": "Suite Luxo"
      },
      {
        "nome": "Ap 1 quarto com sala e cozinha"
      },
      {
        "nome": "Suite Dupla - Ate 6 pessoas"
      }
    ]
  }
}
```

This endpoint retrieves all kittens.

<!-- ### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

| Parameter    | Default | Description                                                                      |
| ------------ | ------- | -------------------------------------------------------------------------------- |
| include_cats | false   | If set to true, the result will also include cats.                               |
| available    | true    | If set to false, the result will include kittens that have already been adopted. |

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside> -->

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require("kittn");

let api = kittn.authorize("meowmeowmeow");
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

| Parameter | Description                      |
| --------- | -------------------------------- |
| ID        | The ID of the kitten to retrieve |

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require("kittn");

let api = kittn.authorize("meowmeowmeow");
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted": ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

| Parameter | Description                    |
| --------- | ------------------------------ |
| ID        | The ID of the kitten to delete |
