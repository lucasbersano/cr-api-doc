# Hotéis

## Buscar todos os estabelecimentos

```shell
curl "https://restapi.crhoteisbrasil.com.br/api/v1/hotels"
  -H "Authorization: sua-chave"
```

```javascript
import axios from "axios";

const api = axios.create({
  baseURL: "https://restapi.crhoteisbrasil.com.br/api/v1",
  timeout: 1000,
  headers: { Authorization: "sua-chave" },
});

api.get("/hotels").then((response) => console.log(response.data));
```

> O comando de cima retornar uma estrutura JSON da seguinte maneira.

```json
{
  "hotels": [
    {
      "hotelId": "0019",
      "hotelName": "Aquaville Hotel",
      "hotelDescription": " Hotel Aquaville",
      "hotelAddress": "Av Beira M",
      "hotelZone": "Praia Linda",
      "hotelCity": "Porto Seguro",
      "hotelState": "BA",
      "hotelPostal": 45810000,
      "hotelDocument": "0",
      "hotelPhone": "7332680124",
      "hotelEmail": "comercial@crsolucoes.com.br",
      "hotelPhoto": "https://orc.in/fotoshotel/0019/1.jpg"
    }
  ]
}
```

Este endpoint retorna todos os estabelecimentos.

### Request HTTP

`GET https://restapi.crhoteisbrasil.com.br/api/v1/hotels`

### Parâmetros de retorno

| Parâmetro        | Descrição                         |
| ---------------- | --------------------------------- |
| hotelId          | Código interno do estabelecimento |
| hotelName        | Nome do estabelecimento           |
| hotelDescription | Descrição do estabelecimento      |
| hotelAddress     | Endereço do estabelecimento       |
| hotelZone        | Bairro do estabelecimento         |
| hotelCity        | Cidade do estabelecimento         |
| hotelState       | Estado do estabelecimento         |
| hotelPostal      | CEP do estabelecimento            |
| hotelDocument    | CNPJ do estabelecimento           |
| hotelPhone       | Telefone de contato               |
| hotelEmail       | Email de reservas                 |
| hotelPhoto       | Fota da hotel                     |

## Buscar um estabelecimento

```shell
curl "https://restapi.crhoteisbrasil.com.br/api/v1/hotels/0019"
  -H "Authorization: sua-chave"
```

```javascript
import axios from "axios";

const api = axios.create({
  baseURL: "https://restapi.crhoteisbrasil.com.br/api/v1",
  timeout: 1000,
  headers: { Authorization: "sua-chave" },
});

api.get("/hotels/0019").then((response) => console.log(response.data));
```

> O comando de cima retornar uma estrutura JSON da seguinte maneira.

```json
{
  "hotel": {
    "hotelId": "0019",
    "hotelName": "Aquaville Hotel",
    "hotelDescription": null,
    "hotelAddress": "Av Beira M",
    "hotelZone": "Praia Linda",
    "hotelCity": "Porto Seguro",
    "hotelState": "BA",
    "hotelPostal": 45810000,
    "hotelDocument": "0",
    "hotelPhone": "7332680124",
    "hotelEmail": "comercial@crsolucoes.com.br",
    "hotelPhoto": "https://orc.in/fotoshotel/0019/1.jpg"
  }
}
```

### HTTP Request

`GET https://restapi.crhoteisbrasil.com.br/api/v1/hotel/:id`

O mesmo parâmetros de retorno são respeitados para busca de um hotel.
