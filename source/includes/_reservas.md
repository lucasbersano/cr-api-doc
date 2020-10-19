# Reservas

## Buscas Reservas

```shell
curl "https://restapi.crhoteisbrasil.com.br/api/v1/hotels/0019/reservations?checkin=2021-02-27&checkout=2021-10-01"
  -H "Authorization: sua-chave"
```

```javascript
import axios from "axios";

const api = axios.create({
  baseURL: "https://restapi.crhoteisbrasil.com.br/api/v1",
  timeout: 1000,
  headers: { Authorization: "sua-chave" },
});

api
  .get("/hotels/:codhotel/reservations?checkin=2021-02-27&checkout=2021-10-01")
  .then((response) => console.log(response.data));
```

> O comando de cima retorna uma estrutura JSON da seguinte maneira.

```json
{
  "reservations": [
    {
      "idreserva": 455649,
      "nome": "João das Neves",
      "cpf": "1111111111",
      "endereco": "Rua do Falcom",
      "bairro": "Millenium",
      "cidade": "Ilha Bela",
      "estado": "SP",
      "cep": 06521032,
      "email": "joao@neves.com",
      "fone": "1111111111",
      "hotel": "0019",
      "acomodacao": "123",
      "entrada": "2021-06-21T00:00:00.000Z",
      "saida": "2021-06-26T00:00:00.000Z",
      "diarias": 5,
      "totalreserva": 1122,
      "formapgto": "mastercard",
      "statuss": "Aprovado_Cielo",
      "identificador": "202010920226056621122"
    }
  ]
}
```

Este endpoint retorna todos os estabelecimentos.

### Request HTTP

`GET https://restapi.crhoteisbrasil.com.br/api/v1/hotels`

### Parâmetros de retorno

| Parâmetro     | Descrição                |
| ------------- | ------------------------ |
| idreserva     | Id da reserva            |
| nome          | Nome do cliente          |
| cpf           | CPF do cliente           |
| endereco      | Endereço do cliente      |
| bairro        | Bairro do cliente        |
| cidade        | Cidade do cliente        |
| estado        | Estado do cliente        |
| cep           | CEP do cliente           |
| email         | Email do cliente         |
| fone          | Telefone do cliente      |
| acomodacao    | Id da acomodação         |
| entrada       | Data de entrada          |
| saida         | Data de Saida            |
| diarias       | Quantidade de diarias    |
| totalreserva  | Total pago pelo reserva  |
| statuss       | Stutus do pagamento      |
| identificador | Identificador da reserva |
