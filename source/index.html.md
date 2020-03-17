---
title: Referencia API

language_tabs:
  - javascript

# toc_footers:
#   - <a href='#'>Sign Up for a Developer Key</a>
#   - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - acomodacoes
  - acomodacoesComTarifario
  - tarifarios

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

A autentificação é feita da seguinte maneira, dentro dos argumentos do query, deve se passar o `chave`. Contate seu administrador para ter acceso a chave.

<aside class="notice">
Lembrese de trocar  <code>sua-chave</code> para sua chave de accesso
</aside>
