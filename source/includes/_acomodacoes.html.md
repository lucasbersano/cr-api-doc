# Acomodações

## Listar acomodações

```javascript
import { request } from "graphql-request";

const query = `{
	acomodacoes(acomodacaoSelect: {chave: "sua-chave"}) {
    nome
  }
}`;
```

> O comando de cima retornar o seguinte JSON

```json
{
  "data": {
    "acomodacoes": [
      {
        "nome": "Ap 3 quartos - Ate 9 pessoas"
      },
      {
        "nome": "Suite Luxo"
      },
      {
        "nome": "Ap 1 quarto com sala e cozinha"
      },
      {
        "nome": "Suite Dupla - Ate 6 pessoas"
      }
    ]
  }
}
```

### Argumentos

| Argumento | Tipo   | Descrição                                               |
| --------- | ------ | ------------------------------------------------------- |
| top       | Int    | Limite na quantidade de resultados                      |
| chave     | String | Chave API                                               |
| codhotel  | String | Codigo do hotel, passe o codigo para filtrar por codigo |

### Paramentros de retorno

| Paramentro                | Tipo   | Descrição                                               |
| ------------------------- | ------ | ------------------------------------------------------- |
| codhotel                  | String | Codigo do Hotel                                         |
| nome                      | String | Nome da acomodação                                      |
| qtd                       | Int    | Quantidade total de acomodação                          |
| maxadt                    | Int    | Quantidade maxima de adultos                            |
| maxchd5                   | Int    | Quantidade maxima de crianças ate 5 anos                |
| chd5free                  | Int    | Quantidade de crianças ate 5 anos que não pagam tarifa  |
| maxchd12                  | Int    | Quantidade maxima de crianças ate 12 anos               |
| chd12free                 | Int    | Quantidade de crianças ate 12 anos que não pagam tarifa |
| minocup                   | Int    | Quantidade mínima de ocupação                           |
| maxocup                   | Int    | Quantidade maxima de ocupação                           |
| descricao                 | String | Descrição da acomodação                                 |
| foto1                     | String | TODO: Descrição                                         |
| foto2                     | String | TODO: Descrição                                         |
| foto3                     | String | TODO: Descrição                                         |
| foto4                     | String | TODO: Descrição                                         |
| frigobar                  | String | TODO: Descrição                                         |
| cofre                     | String | TODO: Descrição                                         |
| tvnormalslim              | String | TODO: Descrição                                         |
| tvlcd                     | String | TODO: Descrição                                         |
| tvacabo                   | String | TODO: Descrição                                         |
| arcondicionado            | String | TODO: Descrição                                         |
| arsplit                   | String | TODO: Descrição                                         |
| ventiladordeteto          | String | TODO: Descrição                                         |
| fechaduraeletronica       | String | TODO: Descrição                                         |
| varandasacada             | String | TODO: Descrição                                         |
| hidromassagem             | String | TODO: Descrição                                         |
| camabox                   | String | TODO: Descrição                                         |
| cortina                   | String | TODO: Descrição                                         |
| secador                   | String | TODO: Descrição                                         |
| naofumante                | String | TODO: Descrição                                         |
| cozinhacompleta           | String | TODO: Descrição                                         |
| saladeestar               | String | TODO: Descrição                                         |
| conjugado                 | String | TODO: Descrição                                         |
| telefone                  | String | TODO: Descrição                                         |
| descricaoingles           | String | TODO: Descrição                                         |
| descricaoespanhol         | String | TODO: Descrição                                         |
| descricaoitaliano         | String | TODO: Descrição                                         |
| nomeingles                | String | TODO: Descrição                                         |
| nomeespanhol              | String | TODO: Descrição                                         |
| nomeitaliano              | String | TODO: Descrição                                         |
| internet                  | String | TODO: Descrição                                         |
| idchannel                 | String | TODO: Descrição                                         |
| descricaocompleta         | String | TODO: Descrição                                         |
| descricaocompletaingles   | String | TODO: Descrição                                         |
| descricaocompletaespanhol | String | TODO: Descrição                                         |
| descricaocompletaitaliano | String | TODO: Descrição                                         |
| idq1c                     | String | TODO: Descrição                                         |
| idq2c                     | String | TODO: Descrição                                         |
| idq3c                     | String | TODO: Descrição                                         |
| idq4c                     | String | TODO: Descrição                                         |
| idq5c                     | String | TODO: Descrição                                         |
| idq6c                     | String | TODO: Descrição                                         |
| idq7c                     | String | TODO: Descrição                                         |
| idq8c                     | String | TODO: Descrição                                         |
| idq9c                     | String | TODO: Descrição                                         |
| idq10c                    | String | TODO: Descrição                                         |
| msgadt                    | String | TODO: Descrição                                         |
| msgadten                  | String | TODO: Descrição                                         |
| msgadtes                  | String | TODO: Descrição                                         |
| msgchd5                   | String | TODO: Descrição                                         |
| msgchd5en                 | String | TODO: Descrição                                         |
| msgchd5es                 | String | TODO: Descrição                                         |
| msgchd12                  | String | TODO: Descrição                                         |
| msgchd12en                | String | TODO: Descrição                                         |
| msgchd12es                | String | TODO: Descrição                                         |
| idnethotel                | String | TODO: Descrição                                         |
| regime                    | String | TODO: Descrição                                         |
| adicionalregime           | Int    | TODO: Descrição                                         |
| naoreembolsavel           | Int    | TODO: Descrição                                         |
| dtnr                      | String | TODO: Descrição                                         |
| ordem                     | Int    | TODO: Descrição                                         |
| idq1                      | String | TODO: Descrição                                         |
| idq2                      | String | TODO: Descrição                                         |
| idq3                      | String | TODO: Descrição                                         |
| idq4                      | String | TODO: Descrição                                         |
| idq5                      | String | TODO: Descrição                                         |
| idq6                      | String | TODO: Descrição                                         |
| idq7                      | String | TODO: Descrição                                         |
| idq8                      | String | TODO: Descrição                                         |
| idq9                      | String | TODO: Descrição                                         |
| idq10                     | String | TODO: Descrição                                         |
| virtual                   | String | TODO: Descrição                                         |
| autonomia                 | String | TODO: Descrição                                         |
| adicionalregimechd1       | Int    | TODO: Descrição                                         |
| adicionalregimechd2       | Int    | TODO: Descrição                                         |
