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
  --data "{
    inicio: '2021-01-22,
    fim: '2021-01-25,
    minimo: 1,
    vagas: 5,
    valorpessoa1: 450
  }"
```

```javascript
import axios from "axios";

const api = axios.create({
  baseURL:
    "https://restapi.crhoteisbrasil.com.br/api/v1/hoteis/0019/acomodacoes/2/tarifario",
  timeout: 1000,
  headers: { Authorization: "sua-chave" },
});

const payload = {
    inicio: '2021-01-22,
    fim: '2021-01-25,
    minimo: 1,
    vagas: 5,
    valorpessoa1: 450
  };

api
  .post("/acomodacoes/2/tarifario", payload)
  .then((response) => console.log(response.data));
```

> O comando de cima retornar uma estrutura JSON da seguinte maneira.

```json
{ "msg": "tarifa criado com sucesso" }
```

Para criar ou atualizar um tarifário, passe o periodo que deseja atualizar e o tarifario para cada quantidade de pessoas.

### Request HTTP

`POST https://restapi.crhoteisbrasil.com.br/api/v1/hoteis/:codhotel/acomodacoes/:idacomodacao/tarifario`

### Parametros de body

| Parametros   | Tipo                            | Descrição                                     |
| ------------ | ------------------------------- | --------------------------------------------- |
| inicio       | Data (YYYY-MM-DD) \*Obrigatorio | Inicio do periodo                             |
| fim          | Data (YYYY-MM-DD) \*Obrigatorio | Fim do periodo                                |
| minimo       | Int \*Obrigatorio               | Mínimo de pessoas requeridas                  |
| vagas        | Int \*Obrigatorio               | Quantidade de vagas disponíveis               |
| valorpessoa1 | Data (YYYY-MM-DD)               | Tarifa em R\$(BRL) para uma (1) pessoas       |
| valorpessoa2 | Data (YYYY-MM-DD)               | Tarifa em R\$(BRL) para duas (2) pessoas      |
| valorpessoa3 | Data (YYYY-MM-DD)               | Tarifa em R\$(BRL) para treis (3) pessoas     |
| valorpessoa4 | Data (YYYY-MM-DD)               | Tarifa em R\$(BRL) para quatro (4) pessoas    |
| valorpessoa5 | Data (YYYY-MM-DD)               | Tarifa em R\$(BRL) para cinco ou mais pessoas |
