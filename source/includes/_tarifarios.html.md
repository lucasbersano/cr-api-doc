# Tarifarios

## Buscar um tarifario

```javascript
import { request } from "graphql-request";

const query = `{
  tarifarios(tarifarioSelect: {	chave: "sua-chave",
    mes: 1,
    ano: 2019,
    day1: 1, 
    day2: 2, 
    codhotel: "0019", 
    acomodacao: "2"}) {
    idtarifario
    adicionalchd5
    adicionalchd12
    mes
    ano
  }
}`;
```

> O comando de cima retornar o seguinte JSON

```json
{
  "data": {
    "tarifarios": [
      {
        "idtarifario": "24268",
        "adicionalchd5": 0,
        "adicionalchd12": 0,
        "mes": 1,
        "ano": 2019
      }
    ]
  }
}
```

### Argumentos

| Argumento  | Tipo   | Descrição       |
| ---------- | ------ | --------------- |
| top        | Int    | TODO: Descrição |
| codhotel   | String | TODO: Descrição |
| acomodacao | String | TODO: Descrição |
| mes        | Int    | TODO: Descrição |
| ano        | Int    | TODO: Descrição |
| dia        | Int    | TODO: Descrição |
| pessoas    | Int    | TODO: Descrição |
| day1       | Int    | TODO: Descrição |
| day2       | Int    | TODO: Descrição |
| orderBy    | String | TODO: Descrição |
| chave      | String | TODO: Descrição |

### Paramentros

| Parametros     | Tipo   | Descrição       |
| -------------- | ------ | --------------- |
| idtarifario    | String | TODO: Descrição |
| mes            | Int    | TODO: Descrição |
| ano            | Int    | TODO: Descrição |
| adicionalchd5  | Int    | TODO: Descrição |
| adicionalchd12 | Int    | TODO: Descrição |
