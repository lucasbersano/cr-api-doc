# Acomodações

## Buscar todas as acomodações de um estabelecimento

```shell
curl "https://restapi.crhoteisbrasil.com.br/api/v1/hotels/0019/rooms"
  -H "Authorization: sua-chave"
```

```javascript
import axios from "axios";

const api = axios.create({
  baseURL: "https://restapi.crhoteisbrasil.com.br/api/v1",
  timeout: 1000,
  headers: { Authorization: "sua-chave" },
});

api.get("/hotels/0019/rooms").then((response) => console.log(response.data));
```

> O comando acima retorna uma estrutura JSON:

```json
{
  "rooms": [
    {
      "roomId": 2,
      "hotelId": "0019",
      "roomName": "Ap 3 quartos - Ate 9 pessoas",
      "maxAdt": 6,
      "maxChd5": 2,
      "chd5Free": 3,
      "maxChd12": 2,
      "chd12Free": 1,
      "minOccupation": 1,
      "maxOccupation": 9,
      "roomDescription": "3 quartos sendo 1 suíte, com ar split, sala com ventilador de teto e TV LCD, cofre, cozinha completa, área de serviço.",
      "minibar": "N",
      "safeBox": "Y",
      "NormalTv": "N",
      "LedTV": "Y",
      "cableTv": "N",
      "airConditioning": "N",
      "splitAirConditioning": "Y",
      "fan": "Y",
      "electronicDoorLock": "N",
      "balcony": "N",
      "jacuzzi": "N",
      "queenBoxBed": "Y",
      "curtain": "N",
      "hairDryer": "N",
      "nonSmoking": "N",
      "kitchen": "Y",
      "living": "Y",
      "connectingRoom": "N",
      "telephone": "N",
      "internet": "N"
    },
    {
      "roomId": 21,
      "hotelId": "0019",
      "roomName": "Suite Luxo",
      "maxAdt": 6,
      "maxChd5": 2,
      "chd5Free": 1,
      "maxChd12": 2,
      "chd12Free": 1,
      "minOccupation": 1,
      "maxOccupation": 9,
      "roomDescription": "Suite com ar split, frigobar,  tv lcd 32 e cofre.",
      "minibar": "Y",
      "safeBox": "Y",
      "NormalTv": "N",
      "LedTV": "Y",
      "cableTv": "N",
      "airConditioning": "N",
      "splitAirConditioning": "Y",
      "fan": "Y",
      "electronicDoorLock": "N",
      "balcony": "N",
      "jacuzzi": "N",
      "queenBoxBed": "Y",
      "curtain": "N",
      "hairDryer": "N",
      "nonSmoking": "N",
      "kitchen": "N",
      "living": "N",
      "connectingRoom": "N",
      "telephone": "N",
      "internet": "N"
    }
  ]
}
```

Este endpoint retorna todos as acomodações com acesso do parceiro

### Request HTTP

`GET https://restapi.crhoteisbrasil.com.br/api/v1/hotels/:hotelId/rooms`

### Parâmetros de retorno

| Parâmetro            | Descrição                                                             |
| -------------------- | --------------------------------------------------------------------- |
| roomId               | ID único da acomodação.                                               |
| hotelId              | Código do estabelecimento que acomodação pertencem.                   |
| roomName             | Nome da acomodação.                                                   |
| maxAdt               | Número máximo de adultos permitidos.                                  |
| maxChd5              | Número máximo de crianças até 5 anos permitidas.                      |
| chd5Free             | Número máximo de crianças até 5 anos permitidas sem pagar adicional.  |
| maxChd12             | Número máximo de crianças até 12 anos permitidas.                     |
| chd12Free            | Número máximo de crianças até 12 anos permitidas sem pagar adicional. |
| minOccupation        | Mínimos permitido de acupação                                         |
| maxOccupation        | Máximo permitido de acupação                                          |
| roomDescription      | Descrição da acomodação.                                              |
| minibar              | Se tem frigobar ("Y" = Sim ou "N" = Não)                              |
| safeBox              | Se tem cofre ("Y" = Sim ou "N" = Não)                                 |
| NormalTv             | Se tem tvnormalslim ("Y" = Sim ou "N" = Não)                          |
| LedTV                | Se tem tvlcd ("Y" = Sim ou "N" = Não)                                 |
| cableTv              | Se tem tvacabo ("Y" = Sim ou "N" = Não)                               |
| airConditioning      | Se tem ar condicionado ("Y" = Sim ou "N" = Não)                       |
| splitAirConditioning | Se tem arsplit ("Y" = Sim ou "N" = Não)                               |
| fan                  | Se tem ventilador de teto ("Y" = Sim ou "N" = Não)                    |
| electronicDoorLock   | Se tem fechadura eletronica ("Y" = Sim ou "N" = Não)                  |
| balcony              | Se tem varanda ou sacada ("Y" = Sim ou "N" = Não)                     |
| jacuzzi              | Se tem hidromassagem ("Y" = Sim ou "N" = Não)                         |
| queenBoxBed          | Se tem camabox ("Y" = Sim ou "N" = Não)                               |
| curtain              | Se tem cortina ("Y" = Sim ou "N" = Não)                               |
| hairDryer            | Se tem secador ("Y" = Sim ou "N" = Não)                               |
| nonSmoking           | Se tem nao fumante ("Y" = Sim ou "N" = Não)                           |
| kitchen              | Se tem cozinhacompleta ("Y" = Sim ou "N" = Não)                       |
| living               | Se tem sala de estar ("Y" = Sim ou "N" = Não)                         |
| connectingRoom       | Se tem conjugado ("Y" = Sim ou "N" = Não)                             |
| telephone            | Se tem telefone ("Y" = Sim ou "N" = Não)                              |
| internet             | Se tem internet ("Y" = Sim ou "N" = Não)                              |

## Buscar uma acomodação

```shell
curl "https://restapi.crhoteisbrasil.com.br/api/v1/hotels/0019/rooms/2"
  -H "Authorization: sua-chave"
```

```javascript
import axios from "axios";

const api = axios.create({
  baseURL: "https://restapi.crhoteisbrasil.com.br/api/v1",
  timeout: 1000,
  headers: { Authorization: "sua-chave" },
});

api.get("/hotels/0019/rooms/2").then((response) => console.log(response.data));
```

> O comando acima retorna uma estrutura JSON:

```json
{
  "rooms": {
    "roomId": 2,
    "hotelId": "0019",
    "roomName": "Ap 3 quartos - Ate 9 pessoas",
    "maxAdt": 6,
    "maxChd5": 2,
    "chd5Free": 3,
    "maxChd12": 2,
    "chd12Free": 1,
    "minOccupation": 1,
    "maxOccupation": 9,
    "roomDescription": "3 quartos sendo 1 suíte, com ar split, sala com ventilador de teto e TV LCD, cofre, cozinha completa, área de serviço.",
    "minibar": "N",
    "safeBox": "Y",
    "NormalTv": "N",
    "LedTV": "Y",
    "cableTv": "N",
    "airConditioning": "N",
    "splitAirConditioning": "Y",
    "fan": "Y",
    "electronicDoorLock": "N",
    "balcony": "N",
    "jacuzzi": "N",
    "queenBoxBed": "Y",
    "curtain": "N",
    "hairDryer": "N",
    "nonSmoking": "N",
    "kitchen": "Y",
    "living": "Y",
    "connectingRoom": "N",
    "telephone": "N",
    "internet": "N"
  }
}
```

### HTTP Request

`GET https://restapi.crhoteisbrasil.com.br/api/v1/hotels/:hotelId/rooms/:roomId`

Os mesmos parâmentros de retorno são respeitados para busca de uma acomodação.
