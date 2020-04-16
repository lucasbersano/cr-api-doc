# Acomodações

## Buscar todas as acomodações

```shell
curl "https://api.crhoteisbrasil.com.br/api/v1/hoteis/0019/tarifario?inicio=2019-02-25&fim=2019-03-05&pessoas=3"
  -H "Authorization: sua-chave"
```

```javascript
import axios from "axios";

const api = axios.create({
  baseURL:
    "https://api.crhoteisbrasil.com.br/api/v1/hoteis/0019/tarifario?inicio=2019-02-25&fim=2019-03-05&pessoas=3",
  timeout: 1000,
  headers: { Authorization: "sua-chave" },
});

api
  .get("/hoteis/0019/tarifario?inicio=2019-02-25&fim=2019-03-05&pessoas=3")
  .then((response) => console.log(response.data));
```

> O comando de cima retornar uma estrura JSON da seguinte maneira.

```json
{
  "acomodacoes": [
    {
      "idacomodacao": 2,
      "descricao": "3 quartos sendo 1 suíte, com ar split, sala com ventilador de teto e TV LCD, cofre, cozinha completa, área de serviço.",
      "maxadt": 6,
      "maxchd5": 2,
      "maxchd12": 2,
      "maxocup": 9,
      "regime": "1",
      "foto": "https://orc.in/fotosacomo/2/1.jpg",
      "tarifarios": {
        "2019-2-28": {
          "valor": 520,
          "disponibilidade": true,
          "dm": 1
        },
        "minimo": 1,
        "regra_minimo": true,
        "disponibilidade": true,
        "total": 520
      }
    },
    {
      "idacomodacao": 21,
      "descricao": "Suite com ar split, frigobar,  tv lcd 32 e cofre.",
      "maxadt": 6,
      "maxchd5": 2,
      "maxchd12": 2,
      "maxocup": 9,
      "regime": "1",
      "foto": "https://orc.in/fotosacomo/21/1.jpg",
      "tarifarios": {
        "2019-2-28": {
          "valor": 210,
          "disponibilidade": true,
          "dm": 1
        },
        "minimo": 1,
        "regra_minimo": true,
        "disponibilidade": true,
        "total": 210
      }
    },
    {
      "idacomodacao": 27,
      "descricao": "1 quarto com ar split, banheiro social, sala com ventilador de teto, tv lcd, cofre, cozinha completa e area de serviço.",
      "maxadt": 3,
      "maxchd5": 1,
      "maxchd12": 1,
      "maxocup": 4,
      "regime": "1",
      "foto": "https://orc.in/fotosacomo/27/1.jpg",
      "tarifarios": {
        "2019-2-28": {
          "valor": 230,
          "disponibilidade": true,
          "dm": 1
        },
        "minimo": 1,
        "regra_minimo": true,
        "disponibilidade": true,
        "total": 230
      }
    },
    {
      "idacomodacao": 192,
      "descricao": "2 suítes com ar split, sala com ventilador de teto e TV LCD, cofre, cozinha completa, área de serviço.",
      "maxadt": 6,
      "maxchd5": 1,
      "maxchd12": 1,
      "maxocup": 7,
      "regime": "1",
      "foto": "https://orc.in/fotosacomo/192/1.jpg",
      "tarifarios": {
        "2019-2-28": {
          "valor": 380,
          "disponibilidade": true,
          "dm": 1
        },
        "minimo": 1,
        "regra_minimo": true,
        "disponibilidade": true,
        "total": 380
      }
    }
  ]
}
```

Este endpoint retornar todos as acomodações com tarifario dos hotel.

### Request HTTP

`GET https://api.crhoteisbrasil.com.br/api/v1/hoteis/<codhotel/tarifaris`

### Parametros de query

| Parâmetro | Tipo                     | Descrição                                |
| --------- | ------------------------ | ---------------------------------------- |
| inicio    | Data format (YYYY-MM-DD) | ID unico da acomodação.                  |
| fim       |                          | Codigo do hotel que acomodação pertecem. |
| pessoas   |                          | Nome da acomodação.                      |
| acomdacao |                          | Nome da acomodação.                      |

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
