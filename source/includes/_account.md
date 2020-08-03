# Accounts

## List all connected accounts

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1/accounts \
  -H 'Accept: application/json' \
  -H 'authorization: string'

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'authorization': 'string'
}

r = requests.get('/api/v1/accounts', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'authorization':'string'
};

fetch('/api/v1/accounts',
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

`GET /api/v1/accounts`

*Retrieve all connected accounts.*

<h3 id="get__api_v1_accounts-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
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
      "id": 0,
      "status": "pending",
      "created_at": "2019-08-24T14:15:22Z",
      "updated_at": "2019-08-24T14:15:22Z",
      "line_of_credit": 0,
      "available_credit": 0,
      "business": {
        "legal_name": "string",
        "name": "string",
        "updated_at": "2019-08-24T14:15:22Z",
        "address": {
          "street_name": "string",
          "street_number": "string",
          "postal_code": "string",
          "district": "string",
          "city": "string",
          "state_code": "string",
          "country": "string",
          "extra_address_info": "string"
        },
        "documents": {
          "virtual": [
            {
              "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
              "value": "string",
              "timestamp": "2019-08-24T14:15:22Z",
              "type": "string",
              "exp": "string",
              "issuer": "string"
            }
          ],
          "physical": [
            {
              "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
              "timestamp": "2019-08-24T14:15:22Z",
              "type": "string",
              "extension": "string"
            }
          ]
        },
        "contact_info": {
          "email": "string",
          "phone_number": "string"
        },
        "created_at": "2019-08-24T14:15:22Z",
        "account_id": 0,
        "business_id": "string"
      },
      "tos_acceptance": {
        "date": "2019-08-24T14:15:22Z",
        "ip": "string",
        "user_agent": "string"
      }
    }
  ]
}
```

<h3 id="get__api_v1_accounts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get__api_v1_accounts-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» page|integer(int32)|true|none|none|
|» total|integer(int32)|true|none|none|
|» data|[object]|true|none|none|
|»» id|integer(int32)|true|none|none|
|»» status|string|true|none|none|
|»» created_at|string(date-time)|true|none|none|
|»» updated_at|string(date-time)|true|none|none|
|»» line_of_credit|number(double)¦null|true|none|none|
|»» available_credit|number(double)¦null|true|none|none|
|»» business|object¦null|true|none|none|
|»»» legal_name|string|true|none|none|
|»»» name|string|true|none|none|
|»»» updated_at|string(date-time)|true|none|none|
|»»» address|object|true|none|none|
|»»»» street_name|string|true|none|none|
|»»»» street_number|string|true|none|none|
|»»»» postal_code|string|true|none|none|
|»»»» district|string|true|none|none|
|»»»» city|string|true|none|none|
|»»»» state_code|string|true|none|none|
|»»»» country|string|true|none|none|
|»»»» extra_address_info|string|false|none|none|
|»»» documents|object|true|none|none|
|»»»» virtual|[object]|false|none|none|
|»»»»» flow-app.schemas.models/VirtualDocument|object|false|none|none|
|»»»»»» id|string(uuid)|true|none|none|
|»»»»»» value|string|true|none|none|
|»»»»»» timestamp|string(date-time)|true|none|none|
|»»»»»» type|string|true|none|none|
|»»»»»» exp|string|false|none|none|
|»»»»»» issuer|string|false|none|none|
|»»»» physical|[object]|false|none|none|
|»»»»» flow.schema/PhysicalDocumentRes|object|false|none|none|
|»»»»»» id|string(uuid)|true|none|none|
|»»»»»» timestamp|string(date-time)|true|none|none|
|»»»»»» type|string|true|none|none|
|»»»»»» extension|string¦null|false|none|none|
|»»» contact_info|object|true|none|none|
|»»»» email|string|true|none|none|
|»»»» phone_number|string|true|none|none|
|»»» created_at|string(date-time)|true|none|none|
|»»» account_id|integer(int32)|true|none|none|
|»»» business_id|string|true|none|none|
|»» tos_acceptance|object¦null|true|none|none|
|»»» date|string(date-time)|true|none|none|
|»»» ip|string|true|none|none|
|»»» user_agent|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|pending|
|status|approved|
|status|under-review|


## Create an account

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1/accounts \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'authorization: string'

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'authorization': 'string'
}

r = requests.post('/api/v1/accounts', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "business": {
    "business_id": "string",
    "name": "string",
    "legal_name": "string",
    "address": {
      "street_name": "string",
      "street_number": "string",
      "postal_code": "string",
      "district": "string",
      "city": "string",
      "state_code": "string",
      "country": "string",
      "extra_address_info": "string"
    },
    "contact_info": {
      "email": "string",
      "phone_number": "string"
    },
    "documents": {
      "physical": [
        {
          "value": "string",
          "type": "CONTRATO-SOCIAL"
        }
      ]
    }
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'authorization':'string'
};

fetch('/api/v1/accounts',
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

`POST /api/v1/accounts`

*Create a new account.*

> Body parameter

```json
{
  "business": {
    "business_id": "string",
    "name": "string",
    "legal_name": "string",
    "address": {
      "street_name": "string",
      "street_number": "string",
      "postal_code": "string",
      "district": "string",
      "city": "string",
      "state_code": "string",
      "country": "string",
      "extra_address_info": "string"
    },
    "contact_info": {
      "email": "string",
      "phone_number": "string"
    },
    "documents": {
      "physical": [
        {
          "value": "string",
          "type": "CONTRATO-SOCIAL"
        }
      ]
    }
  }
}
```

<h3 id="post__api_v1_accounts-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|body|body|object|true|none|
|» business|body|object|false|none|
|»» business_id|body|string|true|none|
|»» name|body|string|true|none|
|»» legal_name|body|string|true|none|
|»» address|body|object|true|none|
|»»» street_name|body|string|true|none|
|»»» street_number|body|string|true|none|
|»»» postal_code|body|string|true|none|
|»»» district|body|string|true|none|
|»»» city|body|string|true|none|
|»»» state_code|body|string|true|none|
|»»» country|body|string|true|none|
|»»» extra_address_info|body|string|false|none|
|»» contact_info|body|object|true|none|
|»»» email|body|string|true|none|
|»»» phone_number|body|string|true|none|
|»» documents|body|object|true|none|
|»»» physical|body|[object]|true|none|
|»»»» flow.schema/BusinessPhysicalDocumentCreate|body|object|false|none|
|»»»»» value|body|string|true|none|
|»»»»» type|body|string|true|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»»»»» type|CONTRATO-SOCIAL|

> Example responses

> 200 Response

```json
{
  "data": {
    "id": 0,
    "status": "pending",
    "created_at": "2019-08-24T14:15:22Z",
    "updated_at": "2019-08-24T14:15:22Z",
    "line_of_credit": 0,
    "available_credit": 0,
    "business": {
      "legal_name": "string",
      "name": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "address": {
        "street_name": "string",
        "street_number": "string",
        "postal_code": "string",
        "district": "string",
        "city": "string",
        "state_code": "string",
        "country": "string",
        "extra_address_info": "string"
      },
      "documents": {
        "virtual": [
          {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "value": "string",
            "timestamp": "2019-08-24T14:15:22Z",
            "type": "string",
            "exp": "string",
            "issuer": "string"
          }
        ],
        "physical": [
          {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "timestamp": "2019-08-24T14:15:22Z",
            "type": "string",
            "extension": "string"
          }
        ]
      },
      "contact_info": {
        "email": "string",
        "phone_number": "string"
      },
      "created_at": "2019-08-24T14:15:22Z",
      "account_id": 0,
      "business_id": "string"
    },
    "tos_acceptance": {
      "date": "2019-08-24T14:15:22Z",
      "ip": "string",
      "user_agent": "string"
    }
  }
}
```

<h3 id="post__api_v1_accounts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="post__api_v1_accounts-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|object|true|none|none|
|»» id|integer(int32)|true|none|none|
|»» status|string|true|none|none|
|»» created_at|string(date-time)|true|none|none|
|»» updated_at|string(date-time)|true|none|none|
|»» line_of_credit|number(double)¦null|true|none|none|
|»» available_credit|number(double)¦null|true|none|none|
|»» business|object¦null|false|none|none|
|»»» legal_name|string|true|none|none|
|»»» name|string|true|none|none|
|»»» updated_at|string(date-time)|true|none|none|
|»»» address|object|true|none|none|
|»»»» street_name|string|true|none|none|
|»»»» street_number|string|true|none|none|
|»»»» postal_code|string|true|none|none|
|»»»» district|string|true|none|none|
|»»»» city|string|true|none|none|
|»»»» state_code|string|true|none|none|
|»»»» country|string|true|none|none|
|»»»» extra_address_info|string|false|none|none|
|»»» documents|object|true|none|none|
|»»»» virtual|[object]|false|none|none|
|»»»»» flow-app.schemas.models/VirtualDocument|object|false|none|none|
|»»»»»» id|string(uuid)|true|none|none|
|»»»»»» value|string|true|none|none|
|»»»»»» timestamp|string(date-time)|true|none|none|
|»»»»»» type|string|true|none|none|
|»»»»»» exp|string|false|none|none|
|»»»»»» issuer|string|false|none|none|
|»»»» physical|[object]|false|none|none|
|»»»»» flow.schema/PhysicalDocumentRes|object|false|none|none|
|»»»»»» id|string(uuid)|true|none|none|
|»»»»»» timestamp|string(date-time)|true|none|none|
|»»»»»» type|string|true|none|none|
|»»»»»» extension|string¦null|false|none|none|
|»»» contact_info|object|true|none|none|
|»»»» email|string|true|none|none|
|»»»» phone_number|string|true|none|none|
|»»» created_at|string(date-time)|true|none|none|
|»»» account_id|integer(int32)|true|none|none|
|»»» business_id|string|true|none|none|
|»» tos_acceptance|object¦null|true|none|none|
|»»» date|string(date-time)|true|none|none|
|»»» ip|string|true|none|none|
|»»» user_agent|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|pending|
|status|approved|
|status|under-review|


## Retrieve an account by id

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1/accounts/{account-id} \
  -H 'Accept: application/json' \
  -H 'authorization: string'

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'authorization': 'string'
}

r = requests.get('/api/v1/accounts/{account-id}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'authorization':'string'
};

fetch('/api/v1/accounts/{account-id}',
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

`GET /api/v1/accounts/{account-id}`

*Retrieve the details of an existing account by account id.*

<h3 id="get__api_v1_accounts_{account-id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|account-id|path|integer(int32)|true|none|

> Example responses

> 200 Response

```json
{
  "data": {
    "id": 0,
    "status": "pending",
    "created_at": "2019-08-24T14:15:22Z",
    "updated_at": "2019-08-24T14:15:22Z",
    "line_of_credit": 0,
    "available_credit": 0,
    "business": {
      "legal_name": "string",
      "name": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "address": {
        "street_name": "string",
        "street_number": "string",
        "postal_code": "string",
        "district": "string",
        "city": "string",
        "state_code": "string",
        "country": "string",
        "extra_address_info": "string"
      },
      "documents": {
        "virtual": [
          {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "value": "string",
            "timestamp": "2019-08-24T14:15:22Z",
            "type": "string",
            "exp": "string",
            "issuer": "string"
          }
        ],
        "physical": [
          {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "timestamp": "2019-08-24T14:15:22Z",
            "type": "string",
            "extension": "string"
          }
        ]
      },
      "contact_info": {
        "email": "string",
        "phone_number": "string"
      },
      "created_at": "2019-08-24T14:15:22Z",
      "account_id": 0,
      "business_id": "string"
    },
    "tos_acceptance": {
      "date": "2019-08-24T14:15:22Z",
      "ip": "string",
      "user_agent": "string"
    }
  }
}
```

<h3 id="get__api_v1_accounts_{account-id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get__api_v1_accounts_{account-id}-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|object|true|none|none|
|»» id|integer(int32)|true|none|none|
|»» status|string|true|none|none|
|»» created_at|string(date-time)|true|none|none|
|»» updated_at|string(date-time)|true|none|none|
|»» line_of_credit|number(double)¦null|true|none|none|
|»» available_credit|number(double)¦null|true|none|none|
|»» business|object¦null|false|none|none|
|»»» legal_name|string|true|none|none|
|»»» name|string|true|none|none|
|»»» updated_at|string(date-time)|true|none|none|
|»»» address|object|true|none|none|
|»»»» street_name|string|true|none|none|
|»»»» street_number|string|true|none|none|
|»»»» postal_code|string|true|none|none|
|»»»» district|string|true|none|none|
|»»»» city|string|true|none|none|
|»»»» state_code|string|true|none|none|
|»»»» country|string|true|none|none|
|»»»» extra_address_info|string|false|none|none|
|»»» documents|object|true|none|none|
|»»»» virtual|[object]|false|none|none|
|»»»»» flow-app.schemas.models/VirtualDocument|object|false|none|none|
|»»»»»» id|string(uuid)|true|none|none|
|»»»»»» value|string|true|none|none|
|»»»»»» timestamp|string(date-time)|true|none|none|
|»»»»»» type|string|true|none|none|
|»»»»»» exp|string|false|none|none|
|»»»»»» issuer|string|false|none|none|
|»»»» physical|[object]|false|none|none|
|»»»»» flow.schema/PhysicalDocumentRes|object|false|none|none|
|»»»»»» id|string(uuid)|true|none|none|
|»»»»»» timestamp|string(date-time)|true|none|none|
|»»»»»» type|string|true|none|none|
|»»»»»» extension|string¦null|false|none|none|
|»»» contact_info|object|true|none|none|
|»»»» email|string|true|none|none|
|»»»» phone_number|string|true|none|none|
|»»» created_at|string(date-time)|true|none|none|
|»»» account_id|integer(int32)|true|none|none|
|»»» business_id|string|true|none|none|
|»» tos_acceptance|object¦null|true|none|none|
|»»» date|string(date-time)|true|none|none|
|»»» ip|string|true|none|none|
|»»» user_agent|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|pending|
|status|approved|
|status|under-review|

## Delete an account


> Code samples

```shell
# You can also use wget
curl -X DELETE /api/v1/accounts/{account-id} \
  -H 'Accept: application/json' \
  -H 'authorization: string'

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'authorization': 'string'
}

r = requests.delete('/api/v1/accounts/{account-id}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'authorization':'string'
};

fetch('/api/v1/accounts/{account-id}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`DELETE /api/v1/accounts/{account-id}`

*Delete an account by id.*

<h3 id="delete__api_v1_accounts_{account-id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|account-id|path|integer(int32)|true|none|

> Example responses

> 204 Response

```json
"string"
```

<h3 id="delete__api_v1_accounts_{account-id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|none|string|

## Update an account


> Code samples

```shell
# You can also use wget
curl -X PATCH /api/v1/accounts/{account-id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'authorization: string'

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'authorization': 'string'
}

r = requests.patch('/api/v1/accounts/{account-id}', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "business": {
    "business_id": "string",
    "name": "string",
    "legal_name": "string",
    "address": {
      "street_name": "string",
      "street_number": "string",
      "postal_code": "string",
      "district": "string",
      "city": "string",
      "state_code": "string",
      "country": "string",
      "extra_address_info": "string"
    },
    "contact_info": {
      "email": "string",
      "phone_number": "string"
    },
    "documents": {
      "physical": [
        {
          "value": "string",
          "type": "CONTRATO-SOCIAL"
        }
      ]
    }
  },
  "tos_acceptance": {
    "date": "2019-08-24T14:15:22Z",
    "ip": "string",
    "user_agent": "string"
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'authorization':'string'
};

fetch('/api/v1/accounts/{account-id}',
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

`PATCH /api/v1/accounts/{account-id}`

*Update one or many fields of an existing account.*

> Body parameter

```json
{
  "business": {
    "business_id": "string",
    "name": "string",
    "legal_name": "string",
    "address": {
      "street_name": "string",
      "street_number": "string",
      "postal_code": "string",
      "district": "string",
      "city": "string",
      "state_code": "string",
      "country": "string",
      "extra_address_info": "string"
    },
    "contact_info": {
      "email": "string",
      "phone_number": "string"
    },
    "documents": {
      "physical": [
        {
          "value": "string",
          "type": "CONTRATO-SOCIAL"
        }
      ]
    }
  },
  "tos_acceptance": {
    "date": "2019-08-24T14:15:22Z",
    "ip": "string",
    "user_agent": "string"
  }
}
```

<h3 id="patch__api_v1_accounts_{account-id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|account-id|path|integer(int32)|true|none|
|body|body|object|true|none|
|» business|body|object|false|none|
|»» business_id|body|string|true|none|
|»» name|body|string|true|none|
|»» legal_name|body|string|true|none|
|»» address|body|object|true|none|
|»»» street_name|body|string|true|none|
|»»» street_number|body|string|true|none|
|»»» postal_code|body|string|true|none|
|»»» district|body|string|true|none|
|»»» city|body|string|true|none|
|»»» state_code|body|string|true|none|
|»»» country|body|string|true|none|
|»»» extra_address_info|body|string|false|none|
|»» contact_info|body|object|true|none|
|»»» email|body|string|true|none|
|»»» phone_number|body|string|true|none|
|»» documents|body|object|true|none|
|»»» physical|body|[object]|true|none|
|»»»» flow.schema/BusinessPhysicalDocumentCreate|body|object|false|none|
|»»»»» value|body|string|true|none|
|»»»»» type|body|string|true|none|
|» tos_acceptance|body|object|false|none|
|»» date|body|string(date-time)|true|none|
|»» ip|body|string|true|none|
|»» user_agent|body|string|true|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»»»»» type|CONTRATO-SOCIAL|

> Example responses

> 204 Response

```json
"string"
```

<h3 id="patch__api_v1_accounts_{account-id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|none|string|

## List all persons

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1/accounts/{account-id}/persons \
  -H 'Accept: application/json' \
  -H 'authorization: string'

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'authorization': 'string'
}

r = requests.get('/api/v1/accounts/{account-id}/persons', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'authorization':'string'
};

fetch('/api/v1/accounts/{account-id}/persons',
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

`GET /api/v1/accounts/{account-id}/persons`

*Retrieve all persons associated with the account.*

<h3 id="get__api_v1_accounts_{account-id}_persons-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|account-id|path|integer(int32)|true|none|

> Example responses

> 200 Response

```json
{
  "data": [
    {
      "id_number": "string",
      "marital_status": "married",
      "pep": true,
      "id": 0,
      "updated_at": "2019-08-24T14:15:22Z",
      "address": {
        "street_name": "string",
        "street_number": "string",
        "postal_code": "string",
        "district": "string",
        "city": "string",
        "state_code": "string",
        "country": "string",
        "extra_address_info": "string"
      },
      "last_name": "string",
      "first_name": "string",
      "documents": {
        "virtual": [
          {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "value": "string",
            "timestamp": "2019-08-24T14:15:22Z",
            "type": "string",
            "exp": "string",
            "issuer": "string"
          }
        ],
        "physical": [
          {
            "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
            "timestamp": "2019-08-24T14:15:22Z",
            "type": "string",
            "extension": "string"
          }
        ]
      },
      "contact_info": {
        "email": "string",
        "phone_number": "string"
      },
      "created_at": "2019-08-24T14:15:22Z",
      "account_opener": true,
      "account_id": 0
    }
  ]
}
```

<h3 id="get__api_v1_accounts_{account-id}_persons-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get__api_v1_accounts_{account-id}_persons-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|[object]|true|none|none|
|»» id_number|string|true|none|none|
|»» marital_status|string|true|none|none|
|»» pep|boolean|true|none|none|
|»» id|integer(int32)|true|none|none|
|»» updated_at|string(date-time)|true|none|none|
|»» address|object|true|none|none|
|»»» street_name|string|true|none|none|
|»»» street_number|string|true|none|none|
|»»» postal_code|string|true|none|none|
|»»» district|string|true|none|none|
|»»» city|string|true|none|none|
|»»» state_code|string|true|none|none|
|»»» country|string|true|none|none|
|»»» extra_address_info|string|false|none|none|
|»» last_name|string|true|none|none|
|»» first_name|string|true|none|none|
|»» documents|object|true|none|none|
|»»» virtual|[object]|false|none|none|
|»»»» flow-app.schemas.models/VirtualDocument|object|false|none|none|
|»»»»» id|string(uuid)|true|none|none|
|»»»»» value|string|true|none|none|
|»»»»» timestamp|string(date-time)|true|none|none|
|»»»»» type|string|true|none|none|
|»»»»» exp|string|false|none|none|
|»»»»» issuer|string|false|none|none|
|»»» physical|[object]|false|none|none|
|»»»» flow.schema/PhysicalDocumentRes|object|false|none|none|
|»»»»» id|string(uuid)|true|none|none|
|»»»»» timestamp|string(date-time)|true|none|none|
|»»»»» type|string|true|none|none|
|»»»»» extension|string¦null|false|none|none|
|»» contact_info|object|true|none|none|
|»»» email|string|true|none|none|
|»»» phone_number|string|true|none|none|
|»» created_at|string(date-time)|true|none|none|
|»» account_opener|boolean|false|none|none|
|»» account_id|integer(int32)|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|marital_status|married|
|marital_status|legally-separated|
|marital_status|single|
|marital_status|other|
|marital_status|divorced|
|marital_status|widowed|

## Create a person

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1/accounts/{account-id}/persons \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'authorization: string'

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'authorization': 'string'
}

r = requests.post('/api/v1/accounts/{account-id}/persons', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "id_number": "string",
  "marital_status": "married",
  "pep": true,
  "address": {
    "street_name": "string",
    "street_number": "string",
    "postal_code": "string",
    "district": "string",
    "city": "string",
    "state_code": "string",
    "country": "string",
    "extra_address_info": "string"
  },
  "last_name": "string",
  "first_name": "string",
  "documents": {
    "physical": [
      {
        "value": "string",
        "type": "CNH"
      }
    ],
    "virtual": [
      {
        "value": "string",
        "exp": "string",
        "issuer": "string",
        "type": "CNH"
      }
    ]
  },
  "contact_info": {
    "email": "string",
    "phone_number": "string"
  },
  "account_opener": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'authorization':'string'
};

fetch('/api/v1/accounts/{account-id}/persons',
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

`POST /api/v1/accounts/{account-id}/persons`

*Create a new person.*

> Body parameter

```json
{
  "id_number": "string",
  "marital_status": "married",
  "pep": true,
  "address": {
    "street_name": "string",
    "street_number": "string",
    "postal_code": "string",
    "district": "string",
    "city": "string",
    "state_code": "string",
    "country": "string",
    "extra_address_info": "string"
  },
  "last_name": "string",
  "first_name": "string",
  "documents": {
    "physical": [
      {
        "value": "string",
        "type": "CNH"
      }
    ],
    "virtual": [
      {
        "value": "string",
        "exp": "string",
        "issuer": "string",
        "type": "CNH"
      }
    ]
  },
  "contact_info": {
    "email": "string",
    "phone_number": "string"
  },
  "account_opener": true
}
```

<h3 id="post__api_v1_accounts_{account-id}_persons-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|account-id|path|integer(int32)|true|none|
|body|body|object|true|none|
|» id_number|body|string|true|none|
|» marital_status|body|string|true|none|
|» pep|body|boolean|true|none|
|» address|body|object|true|none|
|»» street_name|body|string|true|none|
|»» street_number|body|string|true|none|
|»» postal_code|body|string|true|none|
|»» district|body|string|true|none|
|»» city|body|string|true|none|
|»» state_code|body|string|true|none|
|»» country|body|string|true|none|
|»» extra_address_info|body|string|false|none|
|» last_name|body|string|true|none|
|» first_name|body|string|true|none|
|» documents|body|object|true|none|
|»» physical|body|[object]|true|none|
|»»» flow.schema/PersonPhysicalDocumentCreate|body|object|false|none|
|»»»» value|body|string|true|none|
|»»»» type|body|string|true|none|
|»» virtual|body|[object]|false|none|
|»»» value|body|string|true|none|
|»»» exp|body|string|false|none|
|»»» issuer|body|string|false|none|
|»»» type|body|string|true|none|
|» contact_info|body|object|true|none|
|»» email|body|string|true|none|
|»» phone_number|body|string|true|none|
|» account_opener|body|boolean|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» marital_status|married|
|» marital_status|legally-separated|
|» marital_status|single|
|» marital_status|other|
|» marital_status|divorced|
|» marital_status|widowed|
|»»»» type|CNH|
|»»»» type|RG|
|»»» type|CNH|
|»»» type|RG|

> Example responses

> 200 Response

```json
{
  "data": {
    "id_number": "string",
    "marital_status": "married",
    "pep": true,
    "id": 0,
    "updated_at": "2019-08-24T14:15:22Z",
    "address": {
      "street_name": "string",
      "street_number": "string",
      "postal_code": "string",
      "district": "string",
      "city": "string",
      "state_code": "string",
      "country": "string",
      "extra_address_info": "string"
    },
    "last_name": "string",
    "first_name": "string",
    "documents": {
      "virtual": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "value": "string",
          "timestamp": "2019-08-24T14:15:22Z",
          "type": "string",
          "exp": "string",
          "issuer": "string"
        }
      ],
      "physical": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "timestamp": "2019-08-24T14:15:22Z",
          "type": "string",
          "extension": "string"
        }
      ]
    },
    "contact_info": {
      "email": "string",
      "phone_number": "string"
    },
    "created_at": "2019-08-24T14:15:22Z",
    "account_opener": true,
    "account_id": 0
  }
}
```

<h3 id="post__api_v1_accounts_{account-id}_persons-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="post__api_v1_accounts_{account-id}_persons-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|object|true|none|none|
|»» id_number|string|true|none|none|
|»» marital_status|string|true|none|none|
|»» pep|boolean|true|none|none|
|»» id|integer(int32)|true|none|none|
|»» updated_at|string(date-time)|true|none|none|
|»» address|object|true|none|none|
|»»» street_name|string|true|none|none|
|»»» street_number|string|true|none|none|
|»»» postal_code|string|true|none|none|
|»»» district|string|true|none|none|
|»»» city|string|true|none|none|
|»»» state_code|string|true|none|none|
|»»» country|string|true|none|none|
|»»» extra_address_info|string|false|none|none|
|»» last_name|string|true|none|none|
|»» first_name|string|true|none|none|
|»» documents|object|true|none|none|
|»»» virtual|[object]|false|none|none|
|»»»» flow-app.schemas.models/VirtualDocument|object|false|none|none|
|»»»»» id|string(uuid)|true|none|none|
|»»»»» value|string|true|none|none|
|»»»»» timestamp|string(date-time)|true|none|none|
|»»»»» type|string|true|none|none|
|»»»»» exp|string|false|none|none|
|»»»»» issuer|string|false|none|none|
|»»» physical|[object]|false|none|none|
|»»»» flow.schema/PhysicalDocumentRes|object|false|none|none|
|»»»»» id|string(uuid)|true|none|none|
|»»»»» timestamp|string(date-time)|true|none|none|
|»»»»» type|string|true|none|none|
|»»»»» extension|string¦null|false|none|none|
|»» contact_info|object|true|none|none|
|»»» email|string|true|none|none|
|»»» phone_number|string|true|none|none|
|»» created_at|string(date-time)|true|none|none|
|»» account_opener|boolean|false|none|none|
|»» account_id|integer(int32)|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|marital_status|married|
|marital_status|legally-separated|
|marital_status|single|
|marital_status|other|
|marital_status|divorced|
|marital_status|widowed|

## Retrieve a person

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1/accounts/{account-id}/persons/{person-id} \
  -H 'Accept: application/json' \
  -H 'authorization: string'

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'authorization': 'string'
}

r = requests.get('/api/v1/accounts/{account-id}/persons/{person-id}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'authorization':'string'
};

fetch('/api/v1/accounts/{account-id}/persons/{person-id}',
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

`GET /api/v1/accounts/{account-id}/persons/{person-id}`

*Retrieve a person by id.*

<h3 id="get__api_v1_accounts_{account-id}_persons_{person-id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|account-id|path|integer(int32)|true|none|
|person-id|path|integer(int32)|true|none|

> Example responses

> 200 Response

```json
{
  "data": {
    "id_number": "string",
    "marital_status": "married",
    "pep": true,
    "id": 0,
    "updated_at": "2019-08-24T14:15:22Z",
    "address": {
      "street_name": "string",
      "street_number": "string",
      "postal_code": "string",
      "district": "string",
      "city": "string",
      "state_code": "string",
      "country": "string",
      "extra_address_info": "string"
    },
    "last_name": "string",
    "first_name": "string",
    "documents": {
      "virtual": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "value": "string",
          "timestamp": "2019-08-24T14:15:22Z",
          "type": "string",
          "exp": "string",
          "issuer": "string"
        }
      ],
      "physical": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "timestamp": "2019-08-24T14:15:22Z",
          "type": "string",
          "extension": "string"
        }
      ]
    },
    "contact_info": {
      "email": "string",
      "phone_number": "string"
    },
    "created_at": "2019-08-24T14:15:22Z",
    "account_opener": true,
    "account_id": 0
  }
}
```

<h3 id="get__api_v1_accounts_{account-id}_persons_{person-id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get__api_v1_accounts_{account-id}_persons_{person-id}-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|object|true|none|none|
|»» id_number|string|true|none|none|
|»» marital_status|string|true|none|none|
|»» pep|boolean|true|none|none|
|»» id|integer(int32)|true|none|none|
|»» updated_at|string(date-time)|true|none|none|
|»» address|object|true|none|none|
|»»» street_name|string|true|none|none|
|»»» street_number|string|true|none|none|
|»»» postal_code|string|true|none|none|
|»»» district|string|true|none|none|
|»»» city|string|true|none|none|
|»»» state_code|string|true|none|none|
|»»» country|string|true|none|none|
|»»» extra_address_info|string|false|none|none|
|»» last_name|string|true|none|none|
|»» first_name|string|true|none|none|
|»» documents|object|true|none|none|
|»»» virtual|[object]|false|none|none|
|»»»» flow-app.schemas.models/VirtualDocument|object|false|none|none|
|»»»»» id|string(uuid)|true|none|none|
|»»»»» value|string|true|none|none|
|»»»»» timestamp|string(date-time)|true|none|none|
|»»»»» type|string|true|none|none|
|»»»»» exp|string|false|none|none|
|»»»»» issuer|string|false|none|none|
|»»» physical|[object]|false|none|none|
|»»»» flow.schema/PhysicalDocumentRes|object|false|none|none|
|»»»»» id|string(uuid)|true|none|none|
|»»»»» timestamp|string(date-time)|true|none|none|
|»»»»» type|string|true|none|none|
|»»»»» extension|string¦null|false|none|none|
|»» contact_info|object|true|none|none|
|»»» email|string|true|none|none|
|»»» phone_number|string|true|none|none|
|»» created_at|string(date-time)|true|none|none|
|»» account_opener|boolean|false|none|none|
|»» account_id|integer(int32)|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|marital_status|married|
|marital_status|legally-separated|
|marital_status|single|
|marital_status|other|
|marital_status|divorced|
|marital_status|widowed|

## Delete a person

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/v1/accounts/{account-id}/persons/{person-id} \
  -H 'Accept: application/json' \
  -H 'authorization: string'

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'authorization': 'string'
}

r = requests.delete('/api/v1/accounts/{account-id}/persons/{person-id}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'authorization':'string'
};

fetch('/api/v1/accounts/{account-id}/persons/{person-id}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`DELETE /api/v1/accounts/{account-id}/persons/{person-id}`

*Delete a person.*

<h3 id="delete__api_v1_accounts_{account-id}_persons_{person-id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|account-id|path|integer(int32)|true|none|
|person-id|path|integer(int32)|true|none|

> Example responses

> 204 Response

```json
"string"
```

<h3 id="delete__api_v1_accounts_{account-id}_persons_{person-id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|none|string|

## Update a person

> Code samples

```shell
# You can also use wget
curl -X PATCH /api/v1/accounts/{account-id}/persons/{person-id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'authorization: string'

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'authorization': 'string'
}

r = requests.patch('/api/v1/accounts/{account-id}/persons/{person-id}', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "id_number": "string",
  "marital_status": "married",
  "pep": true,
  "address": {
    "street_name": "string",
    "street_number": "string",
    "postal_code": "string",
    "district": "string",
    "city": "string",
    "state_code": "string",
    "country": "string",
    "extra_address_info": "string"
  },
  "last_name": "string",
  "first_name": "string",
  "documents": {
    "physical": [
      {
        "value": "string",
        "type": "CNH"
      }
    ],
    "virtual": [
      {
        "value": "string",
        "exp": "string",
        "issuer": "string",
        "type": "CNH"
      }
    ]
  },
  "contact_info": {
    "email": "string",
    "phone_number": "string"
  },
  "account_opener": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'authorization':'string'
};

fetch('/api/v1/accounts/{account-id}/persons/{person-id}',
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

`PATCH /api/v1/accounts/{account-id}/persons/{person-id}`

*Update one or many fields of an existing person.*

> Body parameter

```json
{
  "id_number": "string",
  "marital_status": "married",
  "pep": true,
  "address": {
    "street_name": "string",
    "street_number": "string",
    "postal_code": "string",
    "district": "string",
    "city": "string",
    "state_code": "string",
    "country": "string",
    "extra_address_info": "string"
  },
  "last_name": "string",
  "first_name": "string",
  "documents": {
    "physical": [
      {
        "value": "string",
        "type": "CNH"
      }
    ],
    "virtual": [
      {
        "value": "string",
        "exp": "string",
        "issuer": "string",
        "type": "CNH"
      }
    ]
  },
  "contact_info": {
    "email": "string",
    "phone_number": "string"
  },
  "account_opener": true
}
```

<h3 id="patch__api_v1_accounts_{account-id}_persons_{person-id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|account-id|path|integer(int32)|true|none|
|person-id|path|integer(int32)|true|none|
|body|body|object|true|none|
|» id_number|body|string|false|none|
|» marital_status|body|string|false|none|
|» pep|body|boolean|false|none|
|» address|body|object|false|none|
|»» street_name|body|string|true|none|
|»» street_number|body|string|true|none|
|»» postal_code|body|string|true|none|
|»» district|body|string|true|none|
|»» city|body|string|true|none|
|»» state_code|body|string|true|none|
|»» country|body|string|true|none|
|»» extra_address_info|body|string|false|none|
|» last_name|body|string|false|none|
|» first_name|body|string|false|none|
|» documents|body|object|false|none|
|»» physical|body|[object]|true|none|
|»»» flow.schema/PersonPhysicalDocumentCreate|body|object|false|none|
|»»»» value|body|string|true|none|
|»»»» type|body|string|true|none|
|»» virtual|body|[object]|false|none|
|»»» value|body|string|true|none|
|»»» exp|body|string|false|none|
|»»» issuer|body|string|false|none|
|»»» type|body|string|true|none|
|» contact_info|body|object|false|none|
|»» email|body|string|true|none|
|»» phone_number|body|string|true|none|
|» account_opener|body|boolean|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» marital_status|married|
|» marital_status|legally-separated|
|» marital_status|single|
|» marital_status|other|
|» marital_status|divorced|
|» marital_status|widowed|
|»»»» type|CNH|
|»»»» type|RG|
|»»» type|CNH|
|»»» type|RG|

> Example responses

> 204 Response

```json
"string"
```

<h3 id="patch__api_v1_accounts_{account-id}_persons_{person-id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|none|string|
