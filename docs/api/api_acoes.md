# API de Ações

O documento a seguir tem como função explicar e exemplificar o funcionaento do microsserviço de ações. Esta API te como função fornecer dados sobre ações da B3 - Bolsa de Valores brasileira. Estes dados incluem informações como dados da empresa, histórico de resultados financeiros, histórico de dividendos e rentabilidade da ação.

### Endpoints

#### **Resumo da ação:**

Caminho: `/api/stocks/stock-summary/{ticker}`

Retorno:
```
{
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
    "variationTwelveMonths": number,
    "allPrices": [
        {
            "value": number,
            "priceDate": string
        }
    ]
}
```

#### **Dados da Empresa:**

Caminho: `/api/company/company-info/{id}`

Retorno:
```
{
    "ipo": int,
    "sector": string,
    "segment": string,
    "marketValue": number,
    "equity": number,
    "numberOfPapers": number
}
```

#### **Resultados Financeiros:**

Caminho: `/api/balance-sheet/yearly/{companyId}`

Retorno:
```
[
    [
        string || number || null
    ]
]
```

#### **Dividendos:**

Caminho: `/api/dividends/{ticker}`

Retorno:
```
{
    "dividends": [
        {
            "stocks": {
                "id": int,
                "ticker": string,
                "companies": {
                    "id": int,
                    "name": string,
                    "cnpj": string,
                    "ipo": int,
                    "foundationYear": int,
                    "firmValue": number,
                    "numberOfPapers": number,
                    "marketSegment": string,
                    "sector": string,
                    "segment": string
                },
                "freeFloat": number,
                "tagAlong": number,
                "avgDailyLiquidity": number
            },
            "type": "JSCP",
            "value": number,
            "ownershipDate": string,
            "paymentDate": string,
            "id": int
        }
    ],
    "yearlyPayments": {
        "2023": number,
        "2022": number,
        "2021": number,
        "2020": number,
        "2019": number,
        "2018": number,
        "2017": number,
        "2016": number,
        "2015": number,
        "2014": number
    },
    "paymentMonths": {
        "Julho": number,
        "Junho": number,
        "Abril": number,
        "Janeiro": number,
        "Dezembro": number,
        "Março": number,
        "Fevereiro": number,
        "Setembro": number,
        "Agosto": number,
        "Novembro": number
    },
    "dividendYield": {
        "dividendYieldLastTenYears": number,
        "dividendYieldCurrent": number,
        "dividendYieldLastFiveYears": number
    }
}
```

#### **Indicadores da Ação:**

Caminho: `/api/stocks/indicators/{ticker}`

Retorno:
```
{
    "indicatorValueResponseList": [
        {
            "indicator": string,
            "value": number
        },
    ]
}
```

#### **Precificação:**

Caminho: `/api/stocks/valuation/{ticker}`

Retorno:
```
{
    "targetPriceResponse": {
        "method": string,
        "value": number
    },
    "ceilingPriceResponse": {
        "method": string,
        "value": number
    }
}
```