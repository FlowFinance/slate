# Loans

## Retrieve all loans by Account

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1/loans \
  -H 'Accept: application/json' \
  -H 'authorization: string' \
  -H 'account-id: 0'

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'authorization': 'string',
  'account-id': '0'
}

r = requests.get('/api/v1/loans', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'authorization':'string',
  'account-id':'0'
};

fetch('/api/v1/loans',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`GET /api/v1/loans`

*Retrieve all loans associated with the account-id.*

<h3 id="get__api_v1_loans-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|account-id|header|integer(int32)|true|none|
|page|query|integer(int32)|false|none|
|limit|query|integer(int32)|false|none|

> Example responses

> 200 Response

```json
{
  "page": 0,
  "total": 0,
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "offer_token": "string",
      "account_id": 0,
      "ccb_url": "string",
      "balance": 0,
      "created_at": "2019-08-24T14:15:22Z",
      "details": {
        "pt_br": {
          "vlr_financiado": 0,
          "qtde_parcelas": 0,
          "perc_juros_mensal": 0,
          "perc_cet_mensal": 0,
          "vlr_parcela": 0,
          "vlr_total_divida": 0
        }
      },
      "signature": {
        "date": "2019-08-24T14:15:22Z",
        "ip": "string",
        "user_agent": "string"
      }
    }
  ]
}
```

<h3 id="get__api_v1_loans-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get__api_v1_loans-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» page|integer(int32)|true|none|none|
|» total|integer(int32)|true|none|none|
|» data|[object]|true|none|none|
|»» id|string(uuid)|true|none|none|
|»» offer_token|string|true|none|none|
|»» account_id|integer(int32)|true|none|none|
|»» ccb_url|string|true|none|none|
|»» balance|number(double)|false|none|none|
|»» created_at|string(date-time)|true|none|none|
|»» details|object|true|none|none|
|»»» pt_br|object|true|none|none|
|»»»» vlr_financiado|number(double)|true|none|none|
|»»»» qtde_parcelas|integer(int32)|true|none|none|
|»»»» perc_juros_mensal|number(double)|true|none|none|
|»»»» perc_cet_mensal|number(double)|true|none|none|
|»»»» vlr_parcela|number(double)|true|none|none|
|»»»» vlr_total_divida|number(double)|true|none|none|
|»» signature|object¦null|true|none|none|
|»»» date|string(date-time)|true|none|none|
|»»» ip|string|true|none|none|
|»»» user_agent|string|true|none|none|

## Create a loan

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1/loans \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'authorization: string' \
  -H 'account-id: 0'

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'authorization': 'string',
  'account-id': '0'
}

r = requests.post('/api/v1/loans', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "offer_token": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'authorization':'string',
  'account-id':'0'
};

fetch('/api/v1/loans',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /api/v1/loans`

*Create a loan*

> Body parameter

```json
{
  "offer_token": "string"
}
```

<h3 id="post__api_v1_loans-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|account-id|header|integer(int32)|true|none|
|body|body|object|true|none|
|» offer_token|body|string|true|none|

> Example responses

> 200 Response

```json
{
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "offer_token": "string",
    "account_id": 0,
    "ccb_url": "string",
    "balance": 0,
    "created_at": "2019-08-24T14:15:22Z",
    "details": {
      "pt_br": {
        "vlr_financiado": 0,
        "qtde_parcelas": 0,
        "perc_juros_mensal": 0,
        "perc_cet_mensal": 0,
        "vlr_parcela": 0,
        "vlr_total_divida": 0
      }
    },
    "signature": {
      "date": "2019-08-24T14:15:22Z",
      "ip": "string",
      "user_agent": "string"
    }
  }
}
```

<h3 id="post__api_v1_loans-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="post__api_v1_loans-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|object|true|none|none|
|»» id|string(uuid)|true|none|none|
|»» offer_token|string|true|none|none|
|»» account_id|integer(int32)|true|none|none|
|»» ccb_url|string|true|none|none|
|»» balance|number(double)|false|none|none|
|»» created_at|string(date-time)|true|none|none|
|»» details|object|true|none|none|
|»»» pt_br|object|true|none|none|
|»»»» vlr_financiado|number(double)|true|none|none|
|»»»» qtde_parcelas|integer(int32)|true|none|none|
|»»»» perc_juros_mensal|number(double)|true|none|none|
|»»»» perc_cet_mensal|number(double)|true|none|none|
|»»»» vlr_parcela|number(double)|true|none|none|
|»»»» vlr_total_divida|number(double)|true|none|none|
|»» signature|object¦null|true|none|none|
|»»» date|string(date-time)|true|none|none|
|»»» ip|string|true|none|none|
|»»» user_agent|string|true|none|none|

## Retrieve a loan by id

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1/loans/{id} \
  -H 'Accept: application/json' \
  -H 'authorization: string' \
  -H 'account-id: 0'

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'authorization': 'string',
  'account-id': '0'
}

r = requests.get('/api/v1/loans/{id}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'authorization':'string',
  'account-id':'0'
};

fetch('/api/v1/loans/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`GET /api/v1/loans/{id}`

*Retrieve the details of an existing loan by id.*

<h3 id="get__api_v1_loans_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|account-id|header|integer(int32)|true|none|
|id|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "offer_token": "string",
    "account_id": 0,
    "ccb_url": "string",
    "balance": 0,
    "created_at": "2019-08-24T14:15:22Z",
    "details": {
      "pt_br": {
        "vlr_financiado": 0,
        "qtde_parcelas": 0,
        "perc_juros_mensal": 0,
        "perc_cet_mensal": 0,
        "vlr_parcela": 0,
        "vlr_total_divida": 0
      }
    },
    "signature": {
      "date": "2019-08-24T14:15:22Z",
      "ip": "string",
      "user_agent": "string"
    }
  }
}
```

<h3 id="get__api_v1_loans_{id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get__api_v1_loans_{id}-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|object|true|none|none|
|»» id|string(uuid)|true|none|none|
|»» offer_token|string|true|none|none|
|»» account_id|integer(int32)|true|none|none|
|»» ccb_url|string|true|none|none|
|»» balance|number(double)|false|none|none|
|»» created_at|string(date-time)|true|none|none|
|»» details|object|true|none|none|
|»»» pt_br|object|true|none|none|
|»»»» vlr_financiado|number(double)|true|none|none|
|»»»» qtde_parcelas|integer(int32)|true|none|none|
|»»»» perc_juros_mensal|number(double)|true|none|none|
|»»»» perc_cet_mensal|number(double)|true|none|none|
|»»»» vlr_parcela|number(double)|true|none|none|
|»»»» vlr_total_divida|number(double)|true|none|none|
|»» signature|object¦null|true|none|none|
|»»» date|string(date-time)|true|none|none|
|»»» ip|string|true|none|none|
|»»» user_agent|string|true|none|none|

## Update a Loan

> Code samples

```shell
# You can also use wget
curl -X PATCH /api/v1/loans/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'authorization: string' \
  -H 'account-id: 0'

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'authorization': 'string',
  'account-id': '0'
}

r = requests.patch('/api/v1/loans/{id}', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "signature": {
    "date": "2019-08-24T14:15:22Z",
    "ip": "string",
    "user-agent": "string"
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'authorization':'string',
  'account-id':'0'
};

fetch('/api/v1/loans/{id}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`PATCH /api/v1/loans/{id}`

*Update (and sign) loan*

> Body parameter

```json
{
  "signature": {
    "date": "2019-08-24T14:15:22Z",
    "ip": "string",
    "user-agent": "string"
  }
}
```

<h3 id="patch__api_v1_loans_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|account-id|header|integer(int32)|true|none|
|id|path|string(uuid)|true|none|
|body|body|object|true|none|
|» signature|body|object¦null|true|none|
|»» date|body|string(date-time)|true|none|
|»» ip|body|string|true|none|
|»» user-agent|body|string|true|none|

> Example responses

> 204 Response

```json
"string"
```

<h3 id="patch__api_v1_loans_{id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|none|string|
