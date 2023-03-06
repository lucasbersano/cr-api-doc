# Reservas

## Buscas Reservas

```shell
curl "https://restapi.crhoteisbrasil.com.br/api/v1/hotels/{codhotel}/reservations?checkin=2021-02-27&checkout=2021-10-01"
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
      "idreserva": "cr29070455649",
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
      "parcelas": 1,
      "datacriacao": "2018-03-30T07:26:30.000Z",
      "statuss": "Aprovado_Cielo",
      "identificador": "202010920226056621122",
      "acomodacoes": [
                {
                    "acomodacao": "1188",
                    "nomeacomodacao": "Standard com café da manhã",
                    "adt": 2,
                    "valor": 780,
                    "regime": "1",
                    "roomPhoto": "https://orc.in/fotosacomo/1188/1.jpg"
                },
                {
                    "acomodacao": "1188",
                    "nomeacomodacao": "Standard&nbsp; com café da manhã",
                    "adt": 2,
                    "valor": 780,
                    "regime": "1",
                    "roomPhoto": "https://orc.in/fotosacomo/1188/1.jpg"
                }
            ]
        }
```

Este endpoint retorna todos os estabelecimentos.

### Request HTTP

`GET https://restapi.crhoteisbrasil.com.br/api/v1/hotels/{codhotel}/reservations`

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
| statuss       | Status do pagamento      |
| identificador | Identificador da reserva |
| acomodacao    | Array de objetos com informações das acomodações |
| &emsp;acomodacao     | Id da acomodação     |
| &emsp;nomeacomodacao | Nome da acomodação   |
| &emsp;adt            | Adultos permitidos   |
| &emsp;valor          | Valor da acomodação  |
| &emsp;regime         | Regime da acomodação |
| &emsp;roomPhoto      | Foto da acomodação   |
