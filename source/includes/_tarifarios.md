# Tarifários

## Buscar tarifarios de acomdaçõas

```shell
  curl "http://localhost:3000/api/v1/hotels/0019/rates?checkin=2019-02-27&checkout=2019-03-01&adults=3"
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
  .get("/hotels/0019/rates?checkin=2019-02-27&checkout=2019-03-01&adults=3")
  .then((response) => console.log(response.data));
```

> O comando de cima retorna uma estrutura JSON da seguinte maneira.

```json
{
  "rooms": [
    {
      "roomId": 2,
      "roomName": "Ap 3 quartos - Ate 9 pessoas",
      "hotelId": "0019"
      "roomDescription": "3 quartos sendo 1 suíte, com ar split, sala com ventilador de teto e TV LCD, cofre, cozinha completa, área de serviço.",
      "maxAdt": 6,
      "maxChd5": 2,
      "maxChd12": 2,
      "minOccupation": 2,
      "maxOccupation": 9,
      "roomMeal": "1",
      "roomPhoto": "https://orc.in/fotosacomo/2/1.jpg",
      "rates": {
        "2019-2-27": {
          "price": 520,
          "availability": true,
          "availabilityNumber": 5
        },
        "2019-2-28": {
          "price": 520,
          "availability": true,
          "availabilityNumber": 5
        },
        "2019-3-1": {
          "price": 1200,
          "availability": false,
          "availabilityNumber": 0
        },
        "minimum": 1,
        "minimumRule": true,
        "generalAvailability": false,
        "amount": 2240
      }
    },
    {
      "roomId": 21,
      "roomName": "Suite Luxo",
      "hotelId": "0019",
      "roomDescription": "Suite com ar split, frigobar,  tv lcd 32 e cofre.",
      "maxAdt": 6,
      "maxChd5": 2,
      "maxChd12": 2,
      "minOccupation": 2,
      "maxOccupation": 9,
      "roomMeal": "1",
      "roomPhoto": "https://orc.in/fotosacomo/21/1.jpg",
      "rates": {
        "2019-2-27": {
          "price": 210,
          "availability": true,
          "availabilityNumber": 7
        },
        "2019-2-28": {
          "price": 210,
          "availability": true,
          "availabilityNumber": 7
        },
        "2019-3-1": {
          "price": 520,
          "availability": true,
          "availabilityNumber": 2
        },
        "minimum": 1,
        "minimumRule": true,
        "generalAvailability": true,
        "amount": 940
      }
    }
  ]
}
```

Este endpoint retorna as acomodações com tarifário do estabelecimento. Obrigatório passar o código do estabelecimento, período e quantidade de pessoas. Se passar o id de uma acomodação no parametros, só será pesquisado a disponibilidade dessa acomodação.

### Request HTTP

`GET https://restapi.crhoteisbrasil.com.br/api/v1/hotels/:hotelId/rates`

### Parametros de query

| Parâmetro   | Tipo                       | Descrição                          |
| ----------- | -------------------------- | ---------------------------------- |
| checkin     | (YYYY-MM-DD) \*Obrigatorio | Data de início da pesquisa.        |
| checkout    | (YYYY-MM-DD) \*Obrigatorio | Data de fim da pesquisa.           |
| adults      | Interger \*Obrigatorio     | Numero de adultos                  |
| chd5        | Interger \*Opcional        | Numero de crianças até 5 anos.     |
| chd12       | Interger \*Opcional        | Numero de crianças de 6 a 12 anos. |
| roomId      | Integer \*Opcional         | Id da acomodação.                  |
| coupon_code | String \*Opcional          | Coupon para desconto               |

Parametros de retorno

Parâmetro Descrição

### Parametros de retorno

| Parâmetro                     | Descrição                                                                                |
| ----------------------------- | ---------------------------------------------------------------------------------------- |
| roomId                        | ID único da acomodação.                                                                  |
| roomName                      | Nome da acomodação                                                                       |
| hotelId                       | Codigo do hotel que acomodação pertecem                                                  |
| roomDescription               | Descrição da acomodação                                                                  |
| maxAdt                        | Número máximo de adultos permitidos.                                                     |
| maxChd5                       | Número máximo de crianças até 5 anos permitidas.                                         |
| maxChd12                      | Número máximo de crianças até 12 anos permitidas.                                        |
| minOccupation                 | Mínimos permitido de acupação                                                            |
| maxOccupation                 | Máximo permitido de acupação                                                             |
| roomMeal                      | Regime de alimentação incluído.                                                          |
|                               | 0 - Sem regime                                                                           |
|                               | 1- Café da manhã                                                                         |
|                               | 2- Café e almoço                                                                         |
|                               | 3- Café e jantar                                                                         |
|                               | 99-Café, almoço e jantar                                                                 |
|                               | 100-Tudo incluído                                                                        |
| roomPhoto                     | URL da foto da acomodação.                                                               |
| rates                         | Objeto JSON do tarifáfio.                                                                |
| rate[data]                    | Objeto JSON representado a data pesquisada. Formato YYYY-MM-DD                           |
| rate[data].price              | Valor da díaria na data. Valores em BRL                                                  |
| rate[data].availability       | Se tem vaga para acomodação no dia.Se não houver vagas retorna false                     |
| rate[data].availabilityNumber | Quantidade de vagas disponíveis.                                                         |
| rate.minimum                  | Mínimo requerido para a data pesquisada.                                                 |
| rate.minimumRule              | Valor booleano se o numero de diárias pesquisada cumpre com mínimo requerido para data.- |
| rate.generalAvailability      | Valor booleano se tem disponibilidade a acomodação para todo o período pesquisado.       |
| rate.amount                   | Valor total para a data pesquisada.                                                      |

## Criar um tarifario

```shell
curl "https://restapi.crhoteisbrasil.com.br/api/v1/hotels/0019/rooms/2/rates" \
  -H "Authorization: sua-chave" \
  -H "Content-Type: application/json" \
  --request POST \
  --data "{
    rateCheckin: '2021-01-22,
    rateCheckout: '2021-01-25,
    rateMinimum: 1,
    rateAvailability: 5,
    rate1pax: 450
  }"
```

```javascript
import axios from "axios";

const api = axios.create({
  baseURL:
    "https://restapi.crhoteisbrasil.com.br/api/v1/hotels/0019/rooms/2/rates",
  timeout: 1000,
  headers: { Authorization: "sua-chave" },
});

const payload = {
    rateCheckin: '2021-01-22,
    rateCheckout: '2021-01-25,
    rateMinimum: 1,
    rateAvailability: 5,
    rate1pax: 450
  };

api
  .post("/rooms/2/rates", payload)
  .then((response) => console.log(response.data));
```

> O comando de cima retorna uma estrutura JSON da seguinte maneira.

```json
{ "msg": "tarifa criada com sucesso" }
```

Para criar ou atualizar um tarifário, passe o periodo que deseja atualizar e o tarifario para cada quantidade de pessoas.

### Request HTTP

`POST https://restapi.crhoteisbrasil.com.br/api/v1/hotels/:hotelId/rooms/:roomId/rates`

### Parametros de body

| Parametros       | Tipo                            | Descrição                                                                                                                                                                                                |
| ---------------- | ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| rateCheckin      | Data (YYYY-MM-DD) \*Obrigatorio | Inicio do periodo                                                                                                                                                                                        |
| rateCheckout     | Data (YYYY-MM-DD) \*Obrigatorio | Fim do periodo                                                                                                                                                                                           |
| rateMinimum      | Int \*Obrigatorio               | Mínimo de diárias requeridas no período                                                                                                                                                                  |
| rateAvailability | Int \*Obrigatorio               | Quantidade de vagas disponíveis                                                                                                                                                                          |
| rate1pax         | Int                             | Tarifa em R\$(BRL) para uma (1) pessoas                                                                                                                                                                  |
| rate2pax         | Int                             | Tarifa em R\$(BRL) para duas (2) pessoas                                                                                                                                                                 |
| rate3pax         | Int                             | Tarifa em R\$(BRL) para treis (3) pessoas                                                                                                                                                                |
| rate4pax         | Int                             | Tarifa em R\$(BRL) para quatro (4) pessoas                                                                                                                                                               |
| rate5pax\*       | Int                             | Tarifa em R\$(BRL) para cinco ou mais pessoas                                                                                                                                                            |
| chd5             | Int Min: 0 Maximo: 100          | Valor int proporcional em porcentagem ao valor do duplo. Ec.: Se o valor do duplo for R$ 200,00 e estiver assinalado no campo chd5 o valor 10, será cobrado por adicional da criança o valor de R$ 20,00 |

| appliedCoupon | String | Nome do coupon foi aplicado a tarifa |

| appliedOffer | String | Nome da oferta foi aplicado a tarifa |

| appliedPackage | String | Node do pacote foi aplicado a tarifa |

\*o tarifário para 5 pessoas ou mais obedece a seguinte regra de cáculo: Somamos a tarifa para 4 pessoas e adicionamos o valor especificado rate5pax. Ex.: Se a tarifa rate4pax for 200 e a rate5pax for 50 a diária para 5 pessoas ou mais seria a soma de 250, para 6 pessoas a soma de 300 e assim por diante, sempre somando o valor de rate4pax + rate5pax para cada pessoa acima de 4.
