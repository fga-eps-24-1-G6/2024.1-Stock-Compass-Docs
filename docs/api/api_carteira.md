# API de Carteira

O documento a seguir tem como função explicar e exemplificar o funcionamento do microsserviço de carteira. Esta API tem como função proporcionar a criação, visualização e edição de carteiras de ações fornecidas pela API de ações. A API funciona como um CRUD de duas entidades principais: Carteira e Lançamentos.

## Endpoints

### Carteira

#### **Criação de Carteira:**

Caminho: `/api/wallets/create/`

Método: `POST`

Body:
```
{
    "name": string,
    "externalId": string
}
```

Retorno:
```
{
    "id": int
    "name": string,
    "externalId": string
}
```

#### **Visualização de Carteira:**

Caminho: `/api/wallets/get/{id}`

Método: `GET`

Retorno:
```
{
    "name": string,
    "externalId": string,
    "stocks": [
        {
            "ticker": string,
            "amount": int,
            "avgPrice": number,
            "variation": number
        }
    ],
    "totalValue": number,
    "variation": number
}
```

#### **Visualização de Carteiras de um Usuário:**

Caminho: `/api/wallets/get/user/{externalId}`

Método: `GET`

Retorno:
```
[
    {
        "id": int
        "name": string,
        "externalId": string
    }
]
```

#### **Edição de Carteira:**

Caminho: `/api/wallets/update/{id}`

Método: `PUT`

Body:
```
{
    "name": string,
}
```

Retorno:
```
{
    "id": int
    "name": string,
    "externalId": string
}
```

#### **Deleção de Carteira:**

Caminho: `/api/wallets/delete/{id}`

Método: `DELETE`

### Lançamento

#### **Criação de Lançamento:**

Caminho: `/api/transactions/create/`

Método: `POST`

Body:
```
{
    "walletId": int,
    "ticker": string,
    "price": number,
    "date": string,
    "amount": int,
    "operation": string
}
```

Retorno:
```
{
    "id": int,
    "wallets": {
        "name": string,
        "externalId": string,
        "stocks": [
            {
                "ticker": string,
                "amount": int,
                "avgPrice": number,
                "variation": number
            }
        ],
        "totalValue": number,
        "variation": number
    },
    "stocks": {
        "ticker": string,
        "currentPrice": number,
        "companyName": string,
        "companyId": int,
        "freeFloat": number,
        "tagAlong": number,
        "avgDailyLiquidity": number,
        "categorie": string,
        "variationOneDay": number,
        "variationOneMonth": number,
        "variationTwelveMonths": number
    },
    "price": number,
    "date": string,
    "amount": int,
    "operation": string
}
```

#### **Visualização de Lançamento:**

Caminho: `/api/transactions/get/{id}`

Método: `GET`

Retorno:
```
{
    "id": int,
    "wallets": {
        "name": string,
        "externalId": string,
        "stocks": [
            {
                "ticker": string,
                "amount": int,
                "avgPrice": number,
                "variation": number
            }
        ],
        "totalValue": number,
        "variation": number
    },
    "stocks": {
        "ticker": string,
        "currentPrice": number,
        "companyName": string,
        "companyId": int,
        "freeFloat": number,
        "tagAlong": number,
        "avgDailyLiquidity": number,
        "categorie": string,
        "variationOneDay": number,
        "variationOneMonth": number,
        "variationTwelveMonths": number
    },
    "price": number,
    "date": string,
    "amount": int,
    "operation": string
}
```

#### **Visualização de Lançamentos de uma Carteira:**

Caminho: `/api/transactions/get/wallet/{walletId}`

Método: `GET`

Retorno:
```
{
    "wallet": {
        "name": string,
        "externalId": string,
        "stocks": [
            {
                "ticker": string,
                "amount": int,
                "avgPrice": number,
                "variation": number
            }
        ],
        "totalValue": number,
        "variation": number
    },
    "transactions": [
        {
            "id": int,
            "stocks": {
                "ticker": string,
                "currentPrice": number,
                "companyName": string,
                "companyId": int,
                "freeFloat": number,
                "tagAlong": number,
                "avgDailyLiquidity": number,
                "categorie": string,
                "variationOneDay": number,
                "variationOneMonth": number,
                "variationTwelveMonths": number
            },
            "price": number,
            "date": string,
            "amount": int,
            "operation": string
        }
    ]
}
```

#### **Edição de Lançamento:**

Caminho: `/api/transactions/update/{id}`

Método: `PUT`

Body:
```
{
    "walletId": int,
    "ticker": string,
    "price": number,
    "date": string,
    "amount": int,
    "operation": string
}
```

Retorno:
```
{
    "id": int,
    "wallets": {
        "name": string,
        "externalId": string,
        "stocks": [
            {
                "ticker": string,
                "amount": int,
                "avgPrice": number,
                "variation": number
            }
        ],
        "totalValue": number,
        "variation": number
    },
    "stocks": {
        "ticker": string,
        "currentPrice": number,
        "companyName": string,
        "companyId": int,
        "freeFloat": number,
        "tagAlong": number,
        "avgDailyLiquidity": number,
        "categorie": string,
        "variationOneDay": number,
        "variationOneMonth": number,
        "variationTwelveMonths": number
    },
    "price": number,
    "date": string,
    "amount": int,
    "operation": string
}
```

#### **Deleção de Lançamento:**

Caminho: `/api/transactions/delete/{id}`

Método: `DELETE`
