# Acomodações

## Buscar todas as acomodações

```shell
curl "https://api.crhoteisbrasil.com.br/api/v1/hoteis/0019/acomodacoes"
  -H "Authorization: sua-chave"
```

```javascript
import axios from "axios";

const api = axios.create({
  baseURL: "https://api.crhoteisbrasil.com.br/api/v1",
  timeout: 1000,
  headers: { Authorization: "sua-chave" },
});

api
  .get("/hoteis/0019/acomodacoes")
  .then((response) => console.log(response.data));
```

> O comando de cima retornar uma estrura JSON da seguinte maneira.

```json
{
  "acomodacoes": [
    {
      "idacomodacao": 2,
      "codhotel": "0019",
      "nome": "Ap 3 quartos - Ate 9 pessoas",
      "maxadt": 6,
      "maxchd5": 2,
      "chd5free": 3,
      "maxchd12": 2,
      "chd12free": 1,
      "minocup": 1,
      "maxocup": 9,
      "descricao": "3 quartos sendo 1 suíte, com ar split, sala com ventilador de teto e TV LCD, cofre, cozinha completa, área de serviço.",
      "frigobar": "N",
      "cofre": "Y",
      "tvnormalslim": "N",
      "tvlcd": "Y",
      "tvacabo": "N",
      "arcondicionado": "N",
      "arsplit": "Y",
      "ventiladordeteto": "Y",
      "fechaduraeletronica": "N",
      "varandasacada": "N",
      "hidromassagem": "N",
      "camabox": "Y",
      "cortina": "N",
      "secador": "N",
      "naofumante": "N",
      "cozinhacompleta": "Y",
      "saladeestar": "Y",
      "conjugado": "N",
      "telefone": "N",
      "internet": "N"
    },
    {
      "idacomodacao": 21,
      "codhotel": "0019",
      "nome": "Suite Luxo",
      "maxadt": 6,
      "maxchd5": 2,
      "chd5free": 1,
      "maxchd12": 2,
      "chd12free": 1,
      "minocup": 1,
      "maxocup": 9,
      "descricao": "Suite com ar split, frigobar,  tv lcd 32 e cofre.",
      "frigobar": "Y",
      "cofre": "Y",
      "tvnormalslim": "N",
      "tvlcd": "Y",
      "tvacabo": "N",
      "arcondicionado": "N",
      "arsplit": "Y",
      "ventiladordeteto": "Y",
      "fechaduraeletronica": "N",
      "varandasacada": "N",
      "hidromassagem": "N",
      "camabox": "Y",
      "cortina": "N",
      "secador": "N",
      "naofumante": "N",
      "cozinhacompleta": "N",
      "saladeestar": "N",
      "conjugado": "N",
      "telefone": "N",
      "internet": "N"
    }
  ]
}
```

Este endpoint retornar todos as acomodações com acesso.

### Request HTTP

`GET https://api.crhoteisbrasil.com.br/api/v1/hoteis/<codhotel>/acomodacoes`

### Parametros de retorno

| Parâmetro           | Descrição                                                        |
| ------------------- | ---------------------------------------------------------------- |
| idacomodacao        | ID unico da acomodação.                                          |
| codhotel            | Codigo do hotel que acomodação pertecem.                         |
| nome                | Nome da acomodação.                                              |
| maxadt              | Número máximo de adultos permitidos.                             |
| maxchd5             | Número máximo de crianças até 5 anos permitidas.                 |
| chd5free            | Número máximo de crianças até 5 anos permitidas sem pagar taxa.  |
| maxchd12            | Número máximo de crianças até 12 anos permitidas.                |
| chd12free           | Número máximo de crianças até 12 anos permitidas sem pagar taxa. |
| minocup             | Mínimos permitido de acupação                                    |
| maxocup             | Máximo permitido de acupação                                     |
| descricao           | Descrição da acomodação.                                         |
| frigobar            | Se tem frigobar ("Y" = Sim ou "N" = Não)                         |
| cofre               | Se tem cofre ("Y" = Sim ou "N" = Não)                            |
| tvnormalslim        | Se tem tvnormalslim ("Y" = Sim ou "N" = Não)                     |
| tvlcd               | Se tem tvlcd ("Y" = Sim ou "N" = Não)                            |
| tvacabo             | Se tem tvacabo ("Y" = Sim ou "N" = Não)                          |
| arcondicionado      | Se tem arcondicionado ("Y" = Sim ou "N" = Não)                   |
| arsplit             | Se tem arsplit ("Y" = Sim ou "N" = Não)                          |
| ventiladordeteto    | Se tem ventiladordeteto ("Y" = Sim ou "N" = Não)                 |
| fechaduraeletronica | Se tem fechaduraeletronica ("Y" = Sim ou "N" = Não)              |
| varandasacada       | Se tem varandasacada ("Y" = Sim ou "N" = Não)                    |
| hidromassagem       | Se tem hidromassagem ("Y" = Sim ou "N" = Não)                    |
| camabox             | Se tem camabox ("Y" = Sim ou "N" = Não)                          |
| cortina             | Se tem cortina ("Y" = Sim ou "N" = Não)                          |
| secador             | Se tem secador ("Y" = Sim ou "N" = Não)                          |
| naofumante          | Se tem naofumante ("Y" = Sim ou "N" = Não)                       |
| cozinhacompleta     | Se tem cozinhacompleta ("Y" = Sim ou "N" = Não)                  |
| saladeestar         | Se tem saladeestar ("Y" = Sim ou "N" = Não)                      |
| conjugado           | Se tem conjugado ("Y" = Sim ou "N" = Não)                        |
| telefone            | Se tem telefone ("Y" = Sim ou "N" = Não)                         |
| internet            | Se tem internet ("Y" = Sim ou "N" = Não)                         |

## Buscar uma acomodação especifica

```shell
curl "https://api.crhoteisbrasil.com.br/api/v1/hoteis/0019/acomodacoes/2"
  -H "Authorization: sua-chave"
```

```javascript
import axios from "axios";

const api = axios.create({
  baseURL: "https://api.crhoteisbrasil.com.br/api/v1",
  timeout: 1000,
  headers: { Authorization: "sua-chave" },
});

api
  .get("/hoteis/0019/acomodacoes/2")
  .then((response) => console.log(response.data));
```

> O comando de cima retornar uma estrura JSON da seguinte maneira.

```json
{
  "acomodacao": {
    "idacomodacao": 2,
    "codhotel": "0019",
    "nome": "Ap 3 quartos - Ate 9 pessoas",
    "maxadt": 6,
    "maxchd5": 2,
    "chd5free": 3,
    "maxchd12": 2,
    "chd12free": 1,
    "minocup": 1,
    "maxocup": 9,
    "descricao": "3 quartos sendo 1 suíte, com ar split, sala com ventilador de teto e TV LCD, cofre, cozinha completa, área de serviço.",
    "frigobar": "N",
    "cofre": "Y",
    "tvnormalslim": "N",
    "tvlcd": "Y",
    "tvacabo": "N",
    "arcondicionado": "N",
    "arsplit": "Y",
    "ventiladordeteto": "Y",
    "fechaduraeletronica": "N",
    "varandasacada": "N",
    "hidromassagem": "N",
    "camabox": "Y",
    "cortina": "N",
    "secador": "N",
    "naofumante": "N",
    "cozinhacompleta": "Y",
    "saladeestar": "Y",
    "conjugado": "N",
    "telefone": "N",
    "internet": "N"
  }
}
```

### HTTP Request

`GET https://api.crhoteisbrasil.com.br/api/v1/hoteis/<codhotel>/acomodacoes/<ID>`

O mesmo paramentros de retorno são respeitados para busca de uma acomodação.
