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

| Argumento                  | Tipo    | Descrição       |
| -------------------------- | ------- | --------------- |
| top                        | Int     | TODO: Descrição |
| orderBy                    | String  | TODO: Descrição |
| chave                      | String  | TODO: Descrição |
| codhotel                   | String  | TODO: Descrição |
| autonomiaIsNull            | Boolean | TODO: Descrição |
| maxadtGreatestOrEqualThan  | Int     | TODO: Descrição |
| maxocupGreatestOrEqualThan | Int     | TODO: Descrição |

### Paramentros

| Paramentro                | Tipo   | Descrição       |
| ------------------------- | ------ | --------------- |
| codhotel                  | String | TODO: Descrição |
| nome                      | String | TODO: Descrição |
| qtd                       | Int    | TODO: Descrição |
| maxadt                    | Int    | TODO: Descrição |
| maxchd5                   | Int    | TODO: Descrição |
| chd5free                  | Int    | TODO: Descrição |
| maxchd12                  | Int    | TODO: Descrição |
| chd12free                 | Int    | TODO: Descrição |
| minocup                   | Int    | TODO: Descrição |
| maxocup                   | Int    | TODO: Descrição |
| statuss                   | String | TODO: Descrição |
| descricao                 | String | TODO: Descrição |
| foto1                     | String | TODO: Descrição |
| foto2                     | String | TODO: Descrição |
| foto3                     | String | TODO: Descrição |
| foto4                     | String | TODO: Descrição |
| frigobar                  | String | TODO: Descrição |
| cofre                     | String | TODO: Descrição |
| tvnormalslim              | String | TODO: Descrição |
| tvlcd                     | String | TODO: Descrição |
| tvacabo                   | String | TODO: Descrição |
| arcondicionado            | String | TODO: Descrição |
| arsplit                   | String | TODO: Descrição |
| ventiladordeteto          | String | TODO: Descrição |
| fechaduraeletronica       | String | TODO: Descrição |
| varandasacada             | String | TODO: Descrição |
| hidromassagem             | String | TODO: Descrição |
| camabox                   | String | TODO: Descrição |
| cortina                   | String | TODO: Descrição |
| secador                   | String | TODO: Descrição |
| naofumante                | String | TODO: Descrição |
| cozinhacompleta           | String | TODO: Descrição |
| saladeestar               | String | TODO: Descrição |
| conjugado                 | String | TODO: Descrição |
| telefone                  | String | TODO: Descrição |
| descricaoingles           | String | TODO: Descrição |
| descricaoespanhol         | String | TODO: Descrição |
| descricaoitaliano         | String | TODO: Descrição |
| nomeingles                | String | TODO: Descrição |
| nomeespanhol              | String | TODO: Descrição |
| nomeitaliano              | String | TODO: Descrição |
| internet                  | String | TODO: Descrição |
| idchannel                 | String | TODO: Descrição |
| descricaocompleta         | String | TODO: Descrição |
| descricaocompletaingles   | String | TODO: Descrição |
| descricaocompletaespanhol | String | TODO: Descrição |
| descricaocompletaitaliano | String | TODO: Descrição |
| idq1c                     | String | TODO: Descrição |
| idq2c                     | String | TODO: Descrição |
| idq3c                     | String | TODO: Descrição |
| idq4c                     | String | TODO: Descrição |
| idq5c                     | String | TODO: Descrição |
| idq6c                     | String | TODO: Descrição |
| idq7c                     | String | TODO: Descrição |
| idq8c                     | String | TODO: Descrição |
| idq9c                     | String | TODO: Descrição |
| idq10c                    | String | TODO: Descrição |
| msgadt                    | String | TODO: Descrição |
| msgadten                  | String | TODO: Descrição |
| msgadtes                  | String | TODO: Descrição |
| msgchd5                   | String | TODO: Descrição |
| msgchd5en                 | String | TODO: Descrição |
| msgchd5es                 | String | TODO: Descrição |
| msgchd12                  | String | TODO: Descrição |
| msgchd12en                | String | TODO: Descrição |
| msgchd12es                | String | TODO: Descrição |
| idnethotel                | String | TODO: Descrição |
| regime                    | String | TODO: Descrição |
| adicionalregime           | Int    | TODO: Descrição |
| naoreembolsavel           | Int    | TODO: Descrição |
| dtnr                      | String | TODO: Descrição |
| ordem                     | Int    | TODO: Descrição |
| idq1                      | String | TODO: Descrição |
| idq2                      | String | TODO: Descrição |
| idq3                      | String | TODO: Descrição |
| idq4                      | String | TODO: Descrição |
| idq5                      | String | TODO: Descrição |
| idq6                      | String | TODO: Descrição |
| idq7                      | String | TODO: Descrição |
| idq8                      | String | TODO: Descrição |
| idq9                      | String | TODO: Descrição |
| idq10                     | String | TODO: Descrição |
| virtual                   | String | TODO: Descrição |
| autonomia                 | String | TODO: Descrição |
| adicionalregimechd1       | Int    | TODO: Descrição |
| adicionalregimechd2       | Int    | TODO: Descrição |