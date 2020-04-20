# Tarifários

## Buscar todas os tarifarios e acomdaçõas

```shell
  curl "http://localhost:3000/api/v1/hoteis/0019/tarifario?inicio=2019-02-27&fim=2019-03-01&pessoas=3"
  -H "Authorization: sua-chave"
```

```javascript
import axios from "axios";

const api = axios.create({
  baseURL: "http://localhost:3000/api/v1",
  timeout: 1000,
  headers: { Authorization: "sua-chave" },
});

api
  .get("/hoteis/0019/tarifario?inicio=2019-02-27&fim=2019-03-01&pessoas=3")
  .then((response) => console.log(response.data));
```

> O comando de cima retornar uma estrutura JSON da seguinte maneira.

```json
{
  "acomodacoes": [
    {
      "idacomodacao": 2,
      "nome": "Ap 3 quartos - Ate 9 pessoas",
      "descricao": "3 quartos sendo 1 suíte, com ar split, sala com ventilador de teto e TV LCD, cofre, cozinha completa, área de serviço.",
      "maxadt": 6,
      "maxchd5": 2,
      "maxchd12": 2,
      "maxocup": 9,
      "regime": "1",
      "foto": "https://orc.in/fotosacomo/2/1.jpg",
      "tarifarios": {
        "2019-2-27": {
          "valor": 520,
          "disponibilidade": true,
          "dv": 5
        },
        "2019-2-28": {
          "valor": 520,
          "disponibilidade": true,
          "dv": 5
        },
        "2019-3-1": {
          "valor": 1200,
          "disponibilidade": false,
          "dm": 1
        },
        "minimo": 1,
        "regra_minimo": true,
        "disponibilidade": false,
        "total": 2240
      }
    },
    {
      "idacomodacao": 21,
      "nome": "Suite Luxo",
      "descricao": "Suite com ar split, frigobar,  tv lcd 32 e cofre.",
      "maxadt": 6,
      "maxchd5": 2,
      "maxchd12": 2,
      "maxocup": 9,
      "regime": "1",
      "foto": "https://orc.in/fotosacomo/21/1.jpg",
      "tarifarios": {
        "2019-2-27": {
          "valor": 210,
          "disponibilidade": true,
          "dv": 7
        },
        "2019-2-28": {
          "valor": 210,
          "disponibilidade": true,
          "dv": 7
        },
        "2019-3-1": {
          "valor": 520,
          "disponibilidade": true,
          "dv": 2
        },
        "minimo": 1,
        "regra_minimo": true,
        "disponibilidade": true,
        "total": 940
      }
    },
    {
      "idacomodacao": 27,
      "nome": "Ap 1 quarto com sala e cozinha",
      "descricao": "1 quarto com ar split, banheiro social, sala com ventilador de teto, tv lcd, cofre, cozinha completa e area de serviço.",
      "maxadt": 3,
      "maxchd5": 1,
      "maxchd12": 1,
      "maxocup": 4,
      "regime": "1",
      "foto": "https://orc.in/fotosacomo/27/1.jpg",
      "tarifarios": {
        "2019-2-27": {
          "valor": 230,
          "disponibilidade": true,
          "dv": 5
        },
        "2019-2-28": {
          "valor": 230,
          "disponibilidade": true,
          "dv": 5
        },
        "2019-3-1": {
          "valor": 560,
          "disponibilidade": true,
          "dv": 3
        },
        "minimo": 1,
        "regra_minimo": true,
        "disponibilidade": true,
        "total": 1020
      }
    },
    {
      "idacomodacao": 192,
      "nome": "Suite Dupla - Ate 6 pessoas",
      "descricao": "2 suítes com ar split, sala com ventilador de teto e TV LCD, cofre, cozinha completa, área de serviço.",
      "maxadt": 6,
      "maxchd5": 1,
      "maxchd12": 1,
      "maxocup": 7,
      "regime": "1",
      "foto": "https://orc.in/fotosacomo/192/1.jpg",
      "tarifarios": {
        "2019-2-27": {
          "valor": 380,
          "disponibilidade": true,
          "dv": 20
        },
        "2019-2-28": {
          "valor": 380,
          "disponibilidade": true,
          "dv": 20
        },
        "2019-3-1": {
          "valor": 880,
          "disponibilidade": false,
          "dm": 1
        },
        "minimo": 1,
        "regra_minimo": true,
        "disponibilidade": false,
        "total": 1640
      }
    }
  ]
}
```

Este endpoint retornar as acomodações com tarifário do hotel. Obrigatório passar o código do hotel, data de início e fim e quantidade de pessoas. Se passar o `id` de uma acomodação no parametros, só será pesquisado a disponibilidade dessa acomodação.

### Request HTTP

`GET https://restapi.crhoteisbrasil.com.br/api/v1/hoteis/:codhotel/tarifario`

### Parametros de query

| Parâmetro | Tipo                            | Descrição                      |
| --------- | ------------------------------- | ------------------------------ |
| inicio    | Data (YYYY-MM-DD) \*Obrigatorio | Data de início da pesquiça.    |
| fim       | Data (YYYY-MM-DD) \*Obrigatorio | Data de fim da pesquiça.       |
| pessoas   | Interger (1 a 5) \*Obrigatorio  | Numero de pessoas na reservas. |
| acomdacao | Integer \*Opcional              | Id da acomodação.              |

### Parametros de retorno

| Parâmetro                       | Descrição                                                                                           |
| ------------------------------- | --------------------------------------------------------------------------------------------------- |
| idacomodacao                    | ID único da acomodação.                                                                             |
| nome                            | Nome da acomodação                                                                                  |
| descricao                       | Codigo do hotel que acomodação pertecem.                                                            |
| maxadt                          | Número máximo de adultos permitidos.                                                                |
| maxchd5                         | Número máximo de crianças até 5 anos permitidas.                                                    |
| maxchd12                        | Número máximo de crianças até 12 anos permitidas.                                                   |
| maxocup                         | Número máximo permitido de acupação                                                                 |
| regime                          | Regime da acomodação.                                                                               |
| foto                            | URL da fota da acomodação.                                                                          |
| tarifario                       | Objeto JSON do tarifáfio.                                                                           |
| tarifario[data]                 | Objeto JSON representado a data pesquiçada. Formato YYYY-MM-DD tarifário                            |
| tarifario[data].valor           | Valor da díaria na data. Valores em BRL                                                             |
| tarifario[data].disponibilidade | Se tem vaga para acomodação no dia.                                                                 |
| tarifario[data].dm              | Mínimo de ocupação permitido para a data.                                                           |
| tarifario[data].dv              | Quantidade de vagas disponíveis.                                                                    |
| tarifario.minimo                | Mínimo requerido para a data pesquisada.                                                            |
| tarifario.regra_minimo          | Valor booleano se o numero de pessoas pesquisadas cumpre com mínimo requerido para data pesquisada. |
| tarifario.disponibilidade       | Valor booleano se tem disponibilidade a acomodação para data pesquisada.                            |
| tarifario.total                 | Valor total para a data pesquisada.                                                                 |

## Criar um tarifario

```shell
curl "https://restapi.crhoteisbrasil.com.br/api/v1/hoteis/0019/acomodacoes/2/tarifario" \
  -H "Authorization: sua-chave" \
  -H "Content-Type: application/json" \
  --request POST \
  --data data.json
```

```javascript
import axios from "axios";

const api = axios.create({
  baseURL:
    "https://restapi.crhoteisbrasil.com.br/api/v1/hoteis/0019/acomodacoes/2/tarifario",
  timeout: 1000,
  headers: { Authorization: "sua-chave" },
});

const payload = {};

api
  .post("/acomodacoes/2/tarifario", payload)
  .then((response) => console.log(response.data));
```

> O comando de cima retornar uma estrutura JSON da seguinte maneira.

```json

```

Para criar um novo tarifário, é necessario especificar todo os dados requidos para um novo tarifario, se exite um tarifário para um mes e ano, a API retornar um error. Caso precise atualizar os dados. Utilize o endpoint de `update`

### Request HTTP

`POST https://restapi.crhoteisbrasil.com.br/api/v1/hoteis/:codhotel/acomodacoes/:idacomodacao/tarifario`

### Parametros de body

| Parametros | Tipo              | Descrição                           |
| ---------- | ----------------- | ----------------------------------- |
| mes        | Int \*Obrigatorio | Mês do tarifário                    |
| ano        | Int \*Obrigatorio | Ano do tarifário                    |
| 1d1p       | Int               | Tarifário do 1o diapara 1 pessoas   |
| 1d2p       | Int               | Tarifário do 1o diapara 2 pessoas   |
| 1d3p       | Int               | Tarifário do 1o diapara 3 pessoas   |
| 1d4p       | Int               | Tarifário do 1o diapara 4 pessoas   |
| 1d5p       | Int               | Tarifário do 1o diapara 5 pessoas   |
| 1dv        | Int               | Vagas disponíveis do 1ro dia        |
| 1dm        | Int               | Mínimo de pessoas por acomodação    |
| 2d1p       | Int               | Tarifário do 2o diapara 1 pessoas   |
| 2d2p       | Int               | Tarifário do 2o diapara 2 pessoas   |
| 2d3p       | Int               | Tarifário do 2o diapara 3 pessoas   |
| 2d4p       | Int               | Tarifário do 2o diapara 4 pessoas   |
| 2d5p       | Int               | Tarifário do 2o diapara 5 pessoas   |
| 2dv        | Int               | Vagas disponíveis do 2o dia         |
| 2dm        | Int               | Mínimo de pessoas por acomodação    |
| 3d1p       | Int               | Tarifário do 3o diapara 1 pessoas   |
| 3d2p       | Int               | Tarifário do 3o diapara 2 pessoas   |
| 3d3p       | Int               | Tarifário do 3o diapara 3 pessoas   |
| 3d4p       | Int               | Tarifário do 3o diapara 4 pessoas   |
| 3d5p       | Int               | Tarifário do 3o diapara 5 pessoas   |
| 3dv        | Int               | Vagas disponíveis do 3o dia         |
| 3dm        | Int               | Mínimo de pessoas por acomodação    |
| 4d1p       | Int               | Tarifário do 4o diapara 1 pessoas   |
| 4d2p       | Int               | Tarifário do 4o diapara 2 pessoas   |
| 4d3p       | Int               | Tarifário do 4o diapara 3 pessoas   |
| 4d4p       | Int               | Tarifário do 4o diapara 4 pessoas   |
| 4d5p       | Int               | Tarifário do 4o diapara 5 pessoas   |
| 4dv        | Int               | Vagas disponíveis do 4o dia         |
| 4dm        | Int               | Mínimo de pessoas por acomodação    |
| 5d1p       | Int               | Tarifário do 5o diapara 1 pessoas   |
| 5d2p       | Int               | Tarifário do 5o diapara 2 pessoas   |
| 5d3p       | Int               | Tarifário do 5o diapara 3 pessoas   |
| 5d4p       | Int               | Tarifário do 5o diapara 4 pessoas   |
| 5d5p       | Int               | Tarifário do 5o diapara 5 pessoas   |
| 5dv        | Int               | Vagas disponíveis do 5o dia         |
| 5dm        | Int               | Mínimo de pessoas por acomodação    |
| 6d1p       | Int               | Tarifário do 6o diapara 1 pessoas   |
| 6d2p       | Int               | Tarifário do 6o diapara 2 pessoas   |
| 6d3p       | Int               | Tarifário do 6o diapara 3 pessoas   |
| 6d4p       | Int               | Tarifário do 6o diapara 4 pessoas   |
| 6d5p       | Int               | Tarifário do 6o diapara 5 pessoas   |
| 6dv        | Int               | Vagas disponíveis do 6o dia         |
| 6dm        | Int               | Mínimo de pessoas por acomodação    |
| 7d1p       | Int               | Tarifário do 7o diapara 1 pessoas   |
| 7d2p       | Int               | Tarifário do 7o diapara 2 pessoas   |
| 7d3p       | Int               | Tarifário do 7o diapara 3 pessoas   |
| 7d4p       | Int               | Tarifário do 7o diapara 4 pessoas   |
| 7d5p       | Int               | Tarifário do 7o diapara 5 pessoas   |
| 7dv        | Int               | Vagas disponíveis do 7o dia         |
| 7dm        | Int               | Mínimo de pessoas por acomodação    |
| 8d1p       | Int               | Tarifário do 8o diapara 1 pessoas   |
| 8d2p       | Int               | Tarifário do 8o diapara 2 pessoas   |
| 8d3p       | Int               | Tarifário do 8o diapara 3 pessoas   |
| 8d4p       | Int               | Tarifário do 8o diapara 4 pessoas   |
| 8d5p       | Int               | Tarifário do 8o diapara 5 pessoas   |
| 8dv        | Int               | Vagas disponíveis do 8o dia         |
| 8dm        | Int               | Mínimo de pessoas por acomodação    |
| 9d1p       | Int               | Tarifário do 9o diapara 1 pessoas   |
| 9d2p       | Int               | Tarifário do 9o diapara 2 pessoas   |
| 9d3p       | Int               | Tarifário do 9o diapara 3 pessoas   |
| 9d4p       | Int               | Tarifário do 9o diapara 4 pessoas   |
| 9d5p       | Int               | Tarifário do 9o diapara 5 pessoas   |
| 9dv        | Int               | Vagas disponíveis do 9o dia         |
| 9dm        | Int               | Mínimo de pessoas por acomodação    |
| 10d1p      | Int               | Tarifário do 10o dia para 1 pessoas |
| 10d2p      | Int               | Tarifário do 10o dia para 2 pessoas |
| 10d3p      | Int               | Tarifário do 10o dia para 3 pessoas |
| 10d4p      | Int               | Tarifário do 10o dia para 4 pessoas |
| 10d5p      | Int               | Tarifário do 10o dia para 5 pessoas |
| 10dv       | Int               | Vagas disponíveis do 10o dia        |
| 10dm       | Int               | Mínimo de pessoas por acomodação    |
| 11d1p      | Int               | Tarifário do 11o dia para 1 pessoas |
| 11d2p      | Int               | Tarifário do 11o dia para 2 pessoas |
| 11d3p      | Int               | Tarifário do 11o dia para 3 pessoas |
| 11d4p      | Int               | Tarifário do 11o dia para 4 pessoas |
| 11d5p      | Int               | Tarifário do 11o dia para 5 pessoas |
| 11dv       | Int               | Vagas disponíveis do 11o dia        |
| 11dm       | Int               | Mínimo de pessoas por acomodação    |
| 12d1p      | Int               | Tarifário do 12o dia para 1 pessoas |
| 12d2p      | Int               | Tarifário do 12o dia para 2 pessoas |
| 12d3p      | Int               | Tarifário do 12o dia para 3 pessoas |
| 12d4p      | Int               | Tarifário do 12o dia para 4 pessoas |
| 12d5p      | Int               | Tarifário do 12o dia para 5 pessoas |
| 12dv       | Int               | Vagas disponíveis do 12o dia        |
| 12dm       | Int               | Mínimo de pessoas por acomodação    |
| 13d1p      | Int               | Tarifário do 13o dia para 1 pessoas |
| 13d2p      | Int               | Tarifário do 13o dia para 2 pessoas |
| 13d3p      | Int               | Tarifário do 13o dia para 3 pessoas |
| 13d4p      | Int               | Tarifário do 13o dia para 4 pessoas |
| 13d5p      | Int               | Tarifário do 13o dia para 5 pessoas |
| 13dv       | Int               | Vagas disponíveis do 13o dia        |
| 13dm       | Int               | Mínimo de pessoas por acomodação    |
| 14d1p      | Int               | Tarifário do 14o dia para 1 pessoas |
| 14d2p      | Int               | Tarifário do 14o dia para 2 pessoas |
| 14d3p      | Int               | Tarifário do 14o dia para 3 pessoas |
| 14d4p      | Int               | Tarifário do 14o dia para 4 pessoas |
| 14d5p      | Int               | Tarifário do 14o dia para 5 pessoas |
| 14dv       | Int               | Vagas disponíveis do 14o dia        |
| 14dm       | Int               | Mínimo de pessoas por acomodação    |
| 15d1p      | Int               | Tarifário do 15o dia para 1 pessoas |
| 15d2p      | Int               | Tarifário do 15o dia para 2 pessoas |
| 15d3p      | Int               | Tarifário do 15o dia para 3 pessoas |
| 15d4p      | Int               | Tarifário do 15o dia para 4 pessoas |
| 15d5p      | Int               | Tarifário do 15o dia para 5 pessoas |
| 15dv       | Int               | Vagas disponíveis do 15o dia        |
| 15dm       | Int               | Mínimo de pessoas por acomodação    |
| 16d1p      | Int               | Tarifário do 16o dia para 1 pessoas |
| 16d2p      | Int               | Tarifário do 16o dia para 2 pessoas |
| 16d3p      | Int               | Tarifário do 16o dia para 3 pessoas |
| 16d4p      | Int               | Tarifário do 16o dia para 4 pessoas |
| 16d5p      | Int               | Tarifário do 16o dia para 5 pessoas |
| 16dv       | Int               | Vagas disponíveis do 16o dia        |
| 16dm       | Int               | Mínimo de pessoas por acomodação    |
| 17d1p      | Int               | Tarifário do 17o dia para 1 pessoas |
| 17d2p      | Int               | Tarifário do 17o dia para 2 pessoas |
| 17d3p      | Int               | Tarifário do 17o dia para 3 pessoas |
| 17d4p      | Int               | Tarifário do 17o dia para 4 pessoas |
| 17d5p      | Int               | Tarifário do 17o dia para 5 pessoas |
| 17dv       | Int               | Vagas disponíveis do 17o dia        |
| 17dm       | Int               | Mínimo de pessoas por acomodação    |
| 18d1p      | Int               | Tarifário do 18o dia para 1 pessoas |
| 18d2p      | Int               | Tarifário do 18o dia para 2 pessoas |
| 18d3p      | Int               | Tarifário do 18o dia para 3 pessoas |
| 18d4p      | Int               | Tarifário do 18o dia para 4 pessoas |
| 18d5p      | Int               | Tarifário do 18o dia para 5 pessoas |
| 18dv       | Int               | Vagas disponíveis do 18o dia        |
| 18dm       | Int               | Mínimo de pessoas por acomodação    |
| 19d1p      | Int               | Tarifário do 19o dia para 1 pessoas |
| 19d2p      | Int               | Tarifário do 19o dia para 2 pessoas |
| 19d3p      | Int               | Tarifário do 19o dia para 3 pessoas |
| 19d4p      | Int               | Tarifário do 19o dia para 4 pessoas |
| 19d5p      | Int               | Tarifário do 19o dia para 5 pessoas |
| 19dv       | Int               | Vagas disponíveis do 19o dia        |
| 19dm       | Int               | Mínimo de pessoas por acomodação    |
| 20d1p      | Int               | Tarifário do 20o dia para 1 pessoas |
| 20d2p      | Int               | Tarifário do 20o dia para 2 pessoas |
| 20d3p      | Int               | Tarifário do 20o dia para 3 pessoas |
| 20d4p      | Int               | Tarifário do 20o dia para 4 pessoas |
| 20d5p      | Int               | Tarifário do 20o dia para 5 pessoas |
| 20dv       | Int               | Vagas disponíveis do 20o dia        |
| 20dm       | Int               | Mínimo de pessoas por acomodação    |
| 21d1p      | Int               | Tarifário do 21o dia para 1 pessoas |
| 21d2p      | Int               | Tarifário do 21o dia para 2 pessoas |
| 21d3p      | Int               | Tarifário do 21o dia para 3 pessoas |
| 21d4p      | Int               | Tarifário do 21o dia para 4 pessoas |
| 21d5p      | Int               | Tarifário do 21o dia para 5 pessoas |
| 21dv       | Int               | Vagas disponíveis do 21o dia        |
| 21dm       | Int               | Mínimo de pessoas por acomodação    |
| 22d1p      | Int               | Tarifário do 22o dia para 1 pessoas |
| 22d2p      | Int               | Tarifário do 22o dia para 2 pessoas |
| 22d3p      | Int               | Tarifário do 22o dia para 3 pessoas |
| 22d4p      | Int               | Tarifário do 22o dia para 4 pessoas |
| 22d5p      | Int               | Tarifário do 22o dia para 5 pessoas |
| 22dv       | Int               | Vagas disponíveis do 22o dia        |
| 22dm       | Int               | Mínimo de pessoas por acomodação    |
| 23d1p      | Int               | Tarifário do 23o dia para 1 pessoas |
| 23d2p      | Int               | Tarifário do 23o dia para 2 pessoas |
| 23d3p      | Int               | Tarifário do 23o dia para 3 pessoas |
| 23d4p      | Int               | Tarifário do 23o dia para 4 pessoas |
| 23d5p      | Int               | Tarifário do 23o dia para 5 pessoas |
| 23dv       | Int               | Vagas disponíveis do 23o dia        |
| 23dm       | Int               | Mínimo de pessoas por acomodação    |
| 24d1p      | Int               | Tarifário do 24o dia para 1 pessoas |
| 24d2p      | Int               | Tarifário do 24o dia para 2 pessoas |
| 24d3p      | Int               | Tarifário do 24o dia para 3 pessoas |
| 24d4p      | Int               | Tarifário do 24o dia para 4 pessoas |
| 24d5p      | Int               | Tarifário do 24o dia para 5 pessoas |
| 24dv       | Int               | Vagas disponíveis do 24o dia        |
| 24dm       | Int               | Mínimo de pessoas por acomodação    |
| 25d1p      | Int               | Tarifário do 25o dia para 1 pessoas |
| 25d2p      | Int               | Tarifário do 25o dia para 2 pessoas |
| 25d3p      | Int               | Tarifário do 25o dia para 3 pessoas |
| 25d4p      | Int               | Tarifário do 25o dia para 4 pessoas |
| 25d5p      | Int               | Tarifário do 25o dia para 5 pessoas |
| 25dv       | Int               | Vagas disponíveis do 25o dia        |
| 25dm       | Int               | Mínimo de pessoas por acomodação    |
| 26d1p      | Int               | Tarifário do 26o dia para 1 pessoas |
| 26d2p      | Int               | Tarifário do 26o dia para 2 pessoas |
| 26d3p      | Int               | Tarifário do 26o dia para 3 pessoas |
| 26d4p      | Int               | Tarifário do 26o dia para 4 pessoas |
| 26d5p      | Int               | Tarifário do 26o dia para 5 pessoas |
| 26dv       | Int               | Vagas disponíveis do 26o dia        |
| 26dm       | Int               | Mínimo de pessoas por acomodação    |
| 27d1p      | Int               | Tarifário do 27o dia para 1 pessoas |
| 27d2p      | Int               | Tarifário do 27o dia para 2 pessoas |
| 27d3p      | Int               | Tarifário do 27o dia para 3 pessoas |
| 27d4p      | Int               | Tarifário do 27o dia para 4 pessoas |
| 27d5p      | Int               | Tarifário do 27o dia para 5 pessoas |
| 27dv       | Int               | Vagas disponíveis do 27o dia        |
| 27dm       | Int               | Mínimo de pessoas por acomodação    |
| 28d1p      | Int               | Tarifário do 28o dia para 1 pessoas |
| 28d2p      | Int               | Tarifário do 28o dia para 2 pessoas |
| 28d3p      | Int               | Tarifário do 28o dia para 3 pessoas |
| 28d4p      | Int               | Tarifário do 28o dia para 4 pessoas |
| 28d5p      | Int               | Tarifário do 28o dia para 5 pessoas |
| 28dv       | Int               | Vagas disponíveis do 28o dia        |
| 28dm       | Int               | Mínimo de pessoas por acomodação    |
| 29d1p      | Int               | Tarifário do 29o dia para 1 pessoas |
| 29d2p      | Int               | Tarifário do 29o dia para 2 pessoas |
| 29d3p      | Int               | Tarifário do 29o dia para 3 pessoas |
| 29d4p      | Int               | Tarifário do 29o dia para 4 pessoas |
| 29d5p      | Int               | Tarifário do 29o dia para 5 pessoas |
| 29dv       | Int               | Vagas disponíveis do 29o dia        |
| 29dm       | Int               | Mínimo de pessoas por acomodação    |
| 30d1p      | Int               | Tarifário do 30o dia para 1 pessoas |
| 30d2p      | Int               | Tarifário do 30o dia para 2 pessoas |
| 30d3p      | Int               | Tarifário do 30o dia para 3 pessoas |
| 30d4p      | Int               | Tarifário do 30o dia para 4 pessoas |
| 30d5p      | Int               | Tarifário do 30o dia para 5 pessoas |
| 30dv       | Int               | Vagas disponíveis do 30o dia        |
| 30dm       | Int               | Mínimo de pessoas por acomodação    |
| 31d1p      | Int               | Tarifário do 31o dia para 1 pessoas |
| 31d2p      | Int               | Tarifário do 31o dia para 2 pessoas |
| 31d3p      | Int               | Tarifário do 31o dia para 3 pessoas |
| 31d4p      | Int               | Tarifário do 31o dia para 4 pessoas |
| 31d5p      | Int               | Tarifário do 31o dia para 5 pessoas |
| 31dv       | Int               | Vagas disponíveis do 31o dia        |
| 31dm       | Int               | Mínimo de pessoas por acomodação    |

## Atualizar um tarifário

```shell
curl "https://restapi.crhoteisbrasil.com.br/api/v1/hoteis/0019/acomodacoes/2/tarifario/12" \
  -H "Authorization: sua-chave" \
  -H "Content-Type: application/json" \
  --request POST \
  --data data.json
```

```javascript
import axios from "axios";

const api = axios.create({
  baseURL:
    "https://restapi.crhoteisbrasil.com.br/api/v1/hoteis/0019/acomodacoes/2/tarifario/12",
  timeout: 1000,
  headers: { Authorization: "sua-chave" },
});

const payload = {};

api
  .post("/acomodacoes/2/tarifario/12", payload)
  .then((response) => console.log(response.data));
```

> O comando de cima retornar uma estrutura JSON da seguinte maneira.

```json

```

Para atualiazer um novo tarifário é necessario so passar os tarifario dos dias que deseja atualizar, o mes e ano não podem ser mudados.

### Request HTTP

`POST https://restapi.crhoteisbrasil.com.br/api/v1/hoteis/:codhotel/acomodacoes/:idacomodacao/tarifario/:idtarifario`

### Parametros de body

| Parametros | Tipo | Descrição                           |
| ---------- | ---- | ----------------------------------- |
| 1d1p       | Int  | Tarifário do 1o diapara 1 pessoas   |
| 1d2p       | Int  | Tarifário do 1o diapara 2 pessoas   |
| 1d3p       | Int  | Tarifário do 1o diapara 3 pessoas   |
| 1d4p       | Int  | Tarifário do 1o diapara 4 pessoas   |
| 1d5p       | Int  | Tarifário do 1o diapara 5 pessoas   |
| 1dv        | Int  | Vagas disponíveis do 1ro dia        |
| 1dm        | Int  | Mínimo de pessoas por acomodação    |
| 2d1p       | Int  | Tarifário do 2o diapara 1 pessoas   |
| 2d2p       | Int  | Tarifário do 2o diapara 2 pessoas   |
| 2d3p       | Int  | Tarifário do 2o diapara 3 pessoas   |
| 2d4p       | Int  | Tarifário do 2o diapara 4 pessoas   |
| 2d5p       | Int  | Tarifário do 2o diapara 5 pessoas   |
| 2dv        | Int  | Vagas disponíveis do 2o dia         |
| 2dm        | Int  | Mínimo de pessoas por acomodação    |
| 3d1p       | Int  | Tarifário do 3o diapara 1 pessoas   |
| 3d2p       | Int  | Tarifário do 3o diapara 2 pessoas   |
| 3d3p       | Int  | Tarifário do 3o diapara 3 pessoas   |
| 3d4p       | Int  | Tarifário do 3o diapara 4 pessoas   |
| 3d5p       | Int  | Tarifário do 3o diapara 5 pessoas   |
| 3dv        | Int  | Vagas disponíveis do 3o dia         |
| 3dm        | Int  | Mínimo de pessoas por acomodação    |
| 4d1p       | Int  | Tarifário do 4o diapara 1 pessoas   |
| 4d2p       | Int  | Tarifário do 4o diapara 2 pessoas   |
| 4d3p       | Int  | Tarifário do 4o diapara 3 pessoas   |
| 4d4p       | Int  | Tarifário do 4o diapara 4 pessoas   |
| 4d5p       | Int  | Tarifário do 4o diapara 5 pessoas   |
| 4dv        | Int  | Vagas disponíveis do 4o dia         |
| 4dm        | Int  | Mínimo de pessoas por acomodação    |
| 5d1p       | Int  | Tarifário do 5o diapara 1 pessoas   |
| 5d2p       | Int  | Tarifário do 5o diapara 2 pessoas   |
| 5d3p       | Int  | Tarifário do 5o diapara 3 pessoas   |
| 5d4p       | Int  | Tarifário do 5o diapara 4 pessoas   |
| 5d5p       | Int  | Tarifário do 5o diapara 5 pessoas   |
| 5dv        | Int  | Vagas disponíveis do 5o dia         |
| 5dm        | Int  | Mínimo de pessoas por acomodação    |
| 6d1p       | Int  | Tarifário do 6o diapara 1 pessoas   |
| 6d2p       | Int  | Tarifário do 6o diapara 2 pessoas   |
| 6d3p       | Int  | Tarifário do 6o diapara 3 pessoas   |
| 6d4p       | Int  | Tarifário do 6o diapara 4 pessoas   |
| 6d5p       | Int  | Tarifário do 6o diapara 5 pessoas   |
| 6dv        | Int  | Vagas disponíveis do 6o dia         |
| 6dm        | Int  | Mínimo de pessoas por acomodação    |
| 7d1p       | Int  | Tarifário do 7o diapara 1 pessoas   |
| 7d2p       | Int  | Tarifário do 7o diapara 2 pessoas   |
| 7d3p       | Int  | Tarifário do 7o diapara 3 pessoas   |
| 7d4p       | Int  | Tarifário do 7o diapara 4 pessoas   |
| 7d5p       | Int  | Tarifário do 7o diapara 5 pessoas   |
| 7dv        | Int  | Vagas disponíveis do 7o dia         |
| 7dm        | Int  | Mínimo de pessoas por acomodação    |
| 8d1p       | Int  | Tarifário do 8o diapara 1 pessoas   |
| 8d2p       | Int  | Tarifário do 8o diapara 2 pessoas   |
| 8d3p       | Int  | Tarifário do 8o diapara 3 pessoas   |
| 8d4p       | Int  | Tarifário do 8o diapara 4 pessoas   |
| 8d5p       | Int  | Tarifário do 8o diapara 5 pessoas   |
| 8dv        | Int  | Vagas disponíveis do 8o dia         |
| 8dm        | Int  | Mínimo de pessoas por acomodação    |
| 9d1p       | Int  | Tarifário do 9o diapara 1 pessoas   |
| 9d2p       | Int  | Tarifário do 9o diapara 2 pessoas   |
| 9d3p       | Int  | Tarifário do 9o diapara 3 pessoas   |
| 9d4p       | Int  | Tarifário do 9o diapara 4 pessoas   |
| 9d5p       | Int  | Tarifário do 9o diapara 5 pessoas   |
| 9dv        | Int  | Vagas disponíveis do 9o dia         |
| 9dm        | Int  | Mínimo de pessoas por acomodação    |
| 10d1p      | Int  | Tarifário do 10o dia para 1 pessoas |
| 10d2p      | Int  | Tarifário do 10o dia para 2 pessoas |
| 10d3p      | Int  | Tarifário do 10o dia para 3 pessoas |
| 10d4p      | Int  | Tarifário do 10o dia para 4 pessoas |
| 10d5p      | Int  | Tarifário do 10o dia para 5 pessoas |
| 10dv       | Int  | Vagas disponíveis do 10o dia        |
| 10dm       | Int  | Mínimo de pessoas por acomodação    |
| 11d1p      | Int  | Tarifário do 11o dia para 1 pessoas |
| 11d2p      | Int  | Tarifário do 11o dia para 2 pessoas |
| 11d3p      | Int  | Tarifário do 11o dia para 3 pessoas |
| 11d4p      | Int  | Tarifário do 11o dia para 4 pessoas |
| 11d5p      | Int  | Tarifário do 11o dia para 5 pessoas |
| 11dv       | Int  | Vagas disponíveis do 11o dia        |
| 11dm       | Int  | Mínimo de pessoas por acomodação    |
| 12d1p      | Int  | Tarifário do 12o dia para 1 pessoas |
| 12d2p      | Int  | Tarifário do 12o dia para 2 pessoas |
| 12d3p      | Int  | Tarifário do 12o dia para 3 pessoas |
| 12d4p      | Int  | Tarifário do 12o dia para 4 pessoas |
| 12d5p      | Int  | Tarifário do 12o dia para 5 pessoas |
| 12dv       | Int  | Vagas disponíveis do 12o dia        |
| 12dm       | Int  | Mínimo de pessoas por acomodação    |
| 13d1p      | Int  | Tarifário do 13o dia para 1 pessoas |
| 13d2p      | Int  | Tarifário do 13o dia para 2 pessoas |
| 13d3p      | Int  | Tarifário do 13o dia para 3 pessoas |
| 13d4p      | Int  | Tarifário do 13o dia para 4 pessoas |
| 13d5p      | Int  | Tarifário do 13o dia para 5 pessoas |
| 13dv       | Int  | Vagas disponíveis do 13o dia        |
| 13dm       | Int  | Mínimo de pessoas por acomodação    |
| 14d1p      | Int  | Tarifário do 14o dia para 1 pessoas |
| 14d2p      | Int  | Tarifário do 14o dia para 2 pessoas |
| 14d3p      | Int  | Tarifário do 14o dia para 3 pessoas |
| 14d4p      | Int  | Tarifário do 14o dia para 4 pessoas |
| 14d5p      | Int  | Tarifário do 14o dia para 5 pessoas |
| 14dv       | Int  | Vagas disponíveis do 14o dia        |
| 14dm       | Int  | Mínimo de pessoas por acomodação    |
| 15d1p      | Int  | Tarifário do 15o dia para 1 pessoas |
| 15d2p      | Int  | Tarifário do 15o dia para 2 pessoas |
| 15d3p      | Int  | Tarifário do 15o dia para 3 pessoas |
| 15d4p      | Int  | Tarifário do 15o dia para 4 pessoas |
| 15d5p      | Int  | Tarifário do 15o dia para 5 pessoas |
| 15dv       | Int  | Vagas disponíveis do 15o dia        |
| 15dm       | Int  | Mínimo de pessoas por acomodação    |
| 16d1p      | Int  | Tarifário do 16o dia para 1 pessoas |
| 16d2p      | Int  | Tarifário do 16o dia para 2 pessoas |
| 16d3p      | Int  | Tarifário do 16o dia para 3 pessoas |
| 16d4p      | Int  | Tarifário do 16o dia para 4 pessoas |
| 16d5p      | Int  | Tarifário do 16o dia para 5 pessoas |
| 16dv       | Int  | Vagas disponíveis do 16o dia        |
| 16dm       | Int  | Mínimo de pessoas por acomodação    |
| 17d1p      | Int  | Tarifário do 17o dia para 1 pessoas |
| 17d2p      | Int  | Tarifário do 17o dia para 2 pessoas |
| 17d3p      | Int  | Tarifário do 17o dia para 3 pessoas |
| 17d4p      | Int  | Tarifário do 17o dia para 4 pessoas |
| 17d5p      | Int  | Tarifário do 17o dia para 5 pessoas |
| 17dv       | Int  | Vagas disponíveis do 17o dia        |
| 17dm       | Int  | Mínimo de pessoas por acomodação    |
| 18d1p      | Int  | Tarifário do 18o dia para 1 pessoas |
| 18d2p      | Int  | Tarifário do 18o dia para 2 pessoas |
| 18d3p      | Int  | Tarifário do 18o dia para 3 pessoas |
| 18d4p      | Int  | Tarifário do 18o dia para 4 pessoas |
| 18d5p      | Int  | Tarifário do 18o dia para 5 pessoas |
| 18dv       | Int  | Vagas disponíveis do 18o dia        |
| 18dm       | Int  | Mínimo de pessoas por acomodação    |
| 19d1p      | Int  | Tarifário do 19o dia para 1 pessoas |
| 19d2p      | Int  | Tarifário do 19o dia para 2 pessoas |
| 19d3p      | Int  | Tarifário do 19o dia para 3 pessoas |
| 19d4p      | Int  | Tarifário do 19o dia para 4 pessoas |
| 19d5p      | Int  | Tarifário do 19o dia para 5 pessoas |
| 19dv       | Int  | Vagas disponíveis do 19o dia        |
| 19dm       | Int  | Mínimo de pessoas por acomodação    |
| 20d1p      | Int  | Tarifário do 20o dia para 1 pessoas |
| 20d2p      | Int  | Tarifário do 20o dia para 2 pessoas |
| 20d3p      | Int  | Tarifário do 20o dia para 3 pessoas |
| 20d4p      | Int  | Tarifário do 20o dia para 4 pessoas |
| 20d5p      | Int  | Tarifário do 20o dia para 5 pessoas |
| 20dv       | Int  | Vagas disponíveis do 20o dia        |
| 20dm       | Int  | Mínimo de pessoas por acomodação    |
| 21d1p      | Int  | Tarifário do 21o dia para 1 pessoas |
| 21d2p      | Int  | Tarifário do 21o dia para 2 pessoas |
| 21d3p      | Int  | Tarifário do 21o dia para 3 pessoas |
| 21d4p      | Int  | Tarifário do 21o dia para 4 pessoas |
| 21d5p      | Int  | Tarifário do 21o dia para 5 pessoas |
| 21dv       | Int  | Vagas disponíveis do 21o dia        |
| 21dm       | Int  | Mínimo de pessoas por acomodação    |
| 22d1p      | Int  | Tarifário do 22o dia para 1 pessoas |
| 22d2p      | Int  | Tarifário do 22o dia para 2 pessoas |
| 22d3p      | Int  | Tarifário do 22o dia para 3 pessoas |
| 22d4p      | Int  | Tarifário do 22o dia para 4 pessoas |
| 22d5p      | Int  | Tarifário do 22o dia para 5 pessoas |
| 22dv       | Int  | Vagas disponíveis do 22o dia        |
| 22dm       | Int  | Mínimo de pessoas por acomodação    |
| 23d1p      | Int  | Tarifário do 23o dia para 1 pessoas |
| 23d2p      | Int  | Tarifário do 23o dia para 2 pessoas |
| 23d3p      | Int  | Tarifário do 23o dia para 3 pessoas |
| 23d4p      | Int  | Tarifário do 23o dia para 4 pessoas |
| 23d5p      | Int  | Tarifário do 23o dia para 5 pessoas |
| 23dv       | Int  | Vagas disponíveis do 23o dia        |
| 23dm       | Int  | Mínimo de pessoas por acomodação    |
| 24d1p      | Int  | Tarifário do 24o dia para 1 pessoas |
| 24d2p      | Int  | Tarifário do 24o dia para 2 pessoas |
| 24d3p      | Int  | Tarifário do 24o dia para 3 pessoas |
| 24d4p      | Int  | Tarifário do 24o dia para 4 pessoas |
| 24d5p      | Int  | Tarifário do 24o dia para 5 pessoas |
| 24dv       | Int  | Vagas disponíveis do 24o dia        |
| 24dm       | Int  | Mínimo de pessoas por acomodação    |
| 25d1p      | Int  | Tarifário do 25o dia para 1 pessoas |
| 25d2p      | Int  | Tarifário do 25o dia para 2 pessoas |
| 25d3p      | Int  | Tarifário do 25o dia para 3 pessoas |
| 25d4p      | Int  | Tarifário do 25o dia para 4 pessoas |
| 25d5p      | Int  | Tarifário do 25o dia para 5 pessoas |
| 25dv       | Int  | Vagas disponíveis do 25o dia        |
| 25dm       | Int  | Mínimo de pessoas por acomodação    |
| 26d1p      | Int  | Tarifário do 26o dia para 1 pessoas |
| 26d2p      | Int  | Tarifário do 26o dia para 2 pessoas |
| 26d3p      | Int  | Tarifário do 26o dia para 3 pessoas |
| 26d4p      | Int  | Tarifário do 26o dia para 4 pessoas |
| 26d5p      | Int  | Tarifário do 26o dia para 5 pessoas |
| 26dv       | Int  | Vagas disponíveis do 26o dia        |
| 26dm       | Int  | Mínimo de pessoas por acomodação    |
| 27d1p      | Int  | Tarifário do 27o dia para 1 pessoas |
| 27d2p      | Int  | Tarifário do 27o dia para 2 pessoas |
| 27d3p      | Int  | Tarifário do 27o dia para 3 pessoas |
| 27d4p      | Int  | Tarifário do 27o dia para 4 pessoas |
| 27d5p      | Int  | Tarifário do 27o dia para 5 pessoas |
| 27dv       | Int  | Vagas disponíveis do 27o dia        |
| 27dm       | Int  | Mínimo de pessoas por acomodação    |
| 28d1p      | Int  | Tarifário do 28o dia para 1 pessoas |
| 28d2p      | Int  | Tarifário do 28o dia para 2 pessoas |
| 28d3p      | Int  | Tarifário do 28o dia para 3 pessoas |
| 28d4p      | Int  | Tarifário do 28o dia para 4 pessoas |
| 28d5p      | Int  | Tarifário do 28o dia para 5 pessoas |
| 28dv       | Int  | Vagas disponíveis do 28o dia        |
| 28dm       | Int  | Mínimo de pessoas por acomodação    |
| 29d1p      | Int  | Tarifário do 29o dia para 1 pessoas |
| 29d2p      | Int  | Tarifário do 29o dia para 2 pessoas |
| 29d3p      | Int  | Tarifário do 29o dia para 3 pessoas |
| 29d4p      | Int  | Tarifário do 29o dia para 4 pessoas |
| 29d5p      | Int  | Tarifário do 29o dia para 5 pessoas |
| 29dv       | Int  | Vagas disponíveis do 29o dia        |
| 29dm       | Int  | Mínimo de pessoas por acomodação    |
| 30d1p      | Int  | Tarifário do 30o dia para 1 pessoas |
| 30d2p      | Int  | Tarifário do 30o dia para 2 pessoas |
| 30d3p      | Int  | Tarifário do 30o dia para 3 pessoas |
| 30d4p      | Int  | Tarifário do 30o dia para 4 pessoas |
| 30d5p      | Int  | Tarifário do 30o dia para 5 pessoas |
| 30dv       | Int  | Vagas disponíveis do 30o dia        |
| 30dm       | Int  | Mínimo de pessoas por acomodação    |
| 31d1p      | Int  | Tarifário do 31o dia para 1 pessoas |
| 31d2p      | Int  | Tarifário do 31o dia para 2 pessoas |
| 31d3p      | Int  | Tarifário do 31o dia para 3 pessoas |
| 31d4p      | Int  | Tarifário do 31o dia para 4 pessoas |
| 31d5p      | Int  | Tarifário do 31o dia para 5 pessoas |
| 31dv       | Int  | Vagas disponíveis do 31o dia        |
| 31dm       | Int  | Mínimo de pessoas por acomodação    |
