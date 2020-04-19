---
title: Referencia de API | Atendimento Total

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript

includes:
  - hoteis
  - acomodacoes
  - tarifarios

search: true
---

# Introdução

Bem-vindo a documentação do Atendimento Total. A API é baseada no padrão REST. Todas as requisições precisa de uma chave api. Entre em contato com seu administrador para obter sua chave de acesso.

O endpoint de produção: `https://restapi.crhoteisbrasil.com.br`

# Autenticação

> Todas as chamas devem enviar a chave de API dentro do cabecalho de "Authorization". Segue um exemplo

```shell
#  Com o shell, é possível passar a chave na chamada.
curl "https://restapi.crhoteisbrasil.com.br/api/v1/hoteis"
  -H "Authorization: sua-chave"
```

```javascript
// Como exemplo utilizaremos a lib axios para requests em javascript.

import axios from "axios";

const api = axios.create({
  baseURL: "https://restapi.crhoteisbrasil.com.br/api/v1",
  timeout: 1000,
  headers: { Authorization: "sua-chave" },
});

api.get("/hoteis").then((response) => console.log(response.data));
```

> Lembre-se de trocar `sua-chave` para sua chave de acesso.

API do atendimento total precisa de chaves de acesso no header Authentication em todas as requisições feitas. Caso a chave não esteja na requisição ou esteja incorreta, uma mensagem de não autorizado será retornada.
