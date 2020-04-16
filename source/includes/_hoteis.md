# Hoteis

## Buscar todos os hoteis

```shell
curl "https://api.crhoteisbrasil.com.br/api/v1/hoteis"
  -H "Authorization: sua-chave"
```

```javascript
import axios from "axios";

const api = axios.create({
  baseURL: "https://api.crhoteisbrasil.com.br/api/v1",
  timeout: 1000,
  headers: { Authorization: "sua-chave" },
});

api.get("/hoteis").then((response) => console.log(response.data));
```

> O comando de cima retornar uma estrura JSON da seguinte maneira.

```json
{
  "hoteis": [
    {
      "codhotel": "0019",
      "nomehotel": "Aquaville Hotel",
      "descricao": " Hotel Aquaville",
      "endereco": "Av Beira M",
      "bairro": "Praia Linda",
      "cidade": "Porto Seguro",
      "estado": "BA",
      "cep": 45810000,
      "cnpj": "0",
      "fone": "7332680124",
      "emailreservas": "comercial@crsolucoes.com.br"
    }
  ]
}
```

Este endpoint retornar todos os hoteis com accesso

### Request HTTP

`GET https://api.crhoteisbrasil.com.br/api/v1/hoteis`

### Parametros de retorno

| Parâmetro     | Descrição           |
| ------------- | ------------------- |
| codhotel      | Código do hotel     |
| nomehotel     | Nome do hotel       |
| descricao     | Decrição do hotel   |
| endereco      | Endereço do hotel   |
| bairro        | Barrio do hotel     |
| cidade        | Cidade do hotel     |
| estado        | Estado do hotel     |
| cep           | CEP do hotel        |
| cnpj          | CNPJ do hotel       |
| fone          | Telefone de contato |
| emailreservas | Email de reservas   |

## Buscar um hotel especifico

```shell
curl "https://api.crhoteisbrasil.com.br/api/v1/hoteis/0019"
  -H "Authorization: sua-chave"
```

```javascript
import axios from "axios";

const api = axios.create({
  baseURL: "https://api.crhoteisbrasil.com.br/api/v1",
  timeout: 1000,
  headers: { Authorization: "sua-chave" },
});

api.get("/hoteis/0019").then((response) => console.log(response.data));
```

> O comando de cima retornar uma estrura JSON da seguinte maneira.

```json
{
  "hotel": {
    "codhotel": "0019",
    "nomehotel": "Aquaville Hotel",
    "descricao": null,
    "endereco": "Av Beira M",
    "bairro": "Praia Linda",
    "cidade": "Porto Seguro",
    "estado": "BA",
    "cep": 45810000,
    "cnpj": "0",
    "fone": "7332680124",
    "emailreservas": "comercial@crsolucoes.com.br"
  }
}
```

### HTTP Request

`GET https://api.crhoteisbrasil.com.br/api/v1/hoteis/:id`

O mesmo paramentros de retorno são respeitados para busca de um hotel
