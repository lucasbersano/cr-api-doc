---
title: Referencia de API

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript

includes:
  - errors

search: true
---

# Introdução

Bem-vindo a documentação do Atendimento Total. A API é baseada no padrão REST. Todas as requicições precisa de uma chave api. Entre em contato com seu administrador para obter seu chave.

O endpoint de produção é https://api.crhoteisbrasil.com.br

# Autenticação

> Todas as chamas devem enviar a chave de API dentro do cabesalho de "Authorization". Segue um exemplo

```shell
#  Com o shell, é possivel pasar o a chave na chamada.
curl "https://api.crhoteisbrasil.com.br/api/v1/hoteis"
  -H "Authorization: sua-chave"
```

```javascript
// Como exemplo utilizaremos a lib axios para request em javascript.

import axios from "axios";

const api = axios.create({
  baseURL: "https://api.crhoteisbrasil.com.br/api/v1",
  timeout: 1000,
  headers: { Authorization: "sua-chave" },
});

api.get("/hoteis").then((response) => console.log(response.data));
```

> Lembrese de trocar `sua-chave` para sua chave de accesso

API do Atendimento total precisa de chaves de API para ter acesso. API espera que a chave esteja em todas as requisições feitas. Caso a chave não esteja na requisição ou esteja incorreta, uma messagem de não autorizado sera retornada.
