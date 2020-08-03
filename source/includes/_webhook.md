# Webhook Endpoints

## List all webhook endpoints

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1/webhook-endpoints \
  -H 'Accept: application/json' \
  -H 'authorization: string'

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'authorization': 'string'
}

r = requests.get('/api/v1/webhook-endpoints', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'authorization':'string'
};

fetch('/api/v1/webhook-endpoints',
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

`GET /api/v1/webhook-endpoints`

*Retrieve all your webhook endpoints.*

<h3 id="get__api_v1_webhook-endpoints-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|

> Example responses

> 200 Response

```json
{
  "data": [
    {
      "id": 0,
      "url": "string",
      "status": "disabled",
      "events": [
        "account.created"
      ],
      "created": "2019-08-24T14:15:22Z",
      "updated": "2019-08-24T14:15:22Z"
    }
  ]
}
```

<h3 id="get__api_v1_webhook-endpoints-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get__api_v1_webhook-endpoints-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|[object]|true|none|none|
|»» flow.schema/Webhook|object|false|none|none|
|»»» id|integer(int32)|true|none|none|
|»»» url|string|true|none|none|
|»»» status|string|true|none|none|
|»»» events|[string]|true|none|none|
|»»» created|string(date-time)|true|none|none|
|»»» updated|string(date-time)|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|disabled|
|status|enabled|

## Create webhook endpoints

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1/webhook-endpoints \
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

r = requests.post('/api/v1/webhook-endpoints', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "url": "string",
  "events": [
    "account.created"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'authorization':'string'
};

fetch('/api/v1/webhook-endpoints',
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

`POST /api/v1/webhook-endpoints`

*Create a new webhook endpoint.*

> Body parameter

```json
{
  "url": "string",
  "events": [
    "account.created"
  ]
}
```

<h3 id="post__api_v1_webhook-endpoints-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|body|body|object|true|none|
|» url|body|string|true|none|
|» events|body|[string]|true|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» events|account.created|
|» events|person.updated|
|» events|account.updated|
|» events|loan.updated|
|» events|loan.created|
|» events|person.created|

> Example responses

> 200 Response

```json
{
  "data": {
    "id": 0,
    "url": "string",
    "status": "disabled",
    "events": [
      "account.created"
    ],
    "created": "2019-08-24T14:15:22Z",
    "updated": "2019-08-24T14:15:22Z"
  }
}
```

<h3 id="post__api_v1_webhook-endpoints-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="post__api_v1_webhook-endpoints-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|object|true|none|none|
|»» id|integer(int32)|true|none|none|
|»» url|string|true|none|none|
|»» status|string|true|none|none|
|»» events|[string]|true|none|none|
|»» created|string(date-time)|true|none|none|
|»» updated|string(date-time)|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|disabled|
|status|enabled|

## Retrieve a webhook endpoint by id

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1/webhook-endpoints/{webhook-id} \
  -H 'Accept: application/json' \
  -H 'authorization: string'

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'authorization': 'string'
}

r = requests.get('/api/v1/webhook-endpoints/{webhook-id}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'authorization':'string'
};

fetch('/api/v1/webhook-endpoints/{webhook-id}',
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

`GET /api/v1/webhook-endpoints/{webhook-id}`

*Retrieve the details of an existing webhook endpoint by webhook id.*

<h3 id="get__api_v1_webhook-endpoints_{webhook-id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|webhook-id|path|integer(int32)|true|none|

> Example responses

> 200 Response

```json
{
  "data": {
    "id": 0,
    "url": "string",
    "status": "disabled",
    "events": [
      "account.created"
    ],
    "created": "2019-08-24T14:15:22Z",
    "updated": "2019-08-24T14:15:22Z"
  }
}
```

<h3 id="get__api_v1_webhook-endpoints_{webhook-id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get__api_v1_webhook-endpoints_{webhook-id}-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|object|true|none|none|
|»» id|integer(int32)|true|none|none|
|»» url|string|true|none|none|
|»» status|string|true|none|none|
|»» events|[string]|true|none|none|
|»» created|string(date-time)|true|none|none|
|»» updated|string(date-time)|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|disabled|
|status|enabled|

## Delete webhook endpoint

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/v1/webhook-endpoints/{webhook-id} \
  -H 'Accept: application/json' \
  -H 'authorization: string'

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'authorization': 'string'
}

r = requests.delete('/api/v1/webhook-endpoints/{webhook-id}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'authorization':'string'
};

fetch('/api/v1/webhook-endpoints/{webhook-id}',
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

`DELETE /api/v1/webhook-endpoints/{webhook-id}`

*Delete a webhook endpoint by id.*

<h3 id="delete__api_v1_webhook-endpoints_{webhook-id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|webhook-id|path|integer(int32)|true|none|

> Example responses

> 204 Response

```json
"string"
```

<h3 id="delete__api_v1_webhook-endpoints_{webhook-id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|none|string|

## Update a webhook endpoint

> Code samples

```shell
# You can also use wget
curl -X PATCH /api/v1/webhook-endpoints/{webhook-id} \
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

r = requests.patch('/api/v1/webhook-endpoints/{webhook-id}', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "url": "string",
  "status": "disabled",
  "events": [
    "account.created"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'authorization':'string'
};

fetch('/api/v1/webhook-endpoints/{webhook-id}',
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

`PATCH /api/v1/webhook-endpoints/{webhook-id}`

*Update one or many fields of an existing webhook endpoint.*

> Body parameter

```json
{
  "url": "string",
  "status": "disabled",
  "events": [
    "account.created"
  ]
}
```

<h3 id="patch__api_v1_webhook-endpoints_{webhook-id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|webhook-id|path|integer(int32)|true|none|
|body|body|object|true|none|
|» url|body|string|false|none|
|» status|body|string|false|none|
|» events|body|[string]|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» status|disabled|
|» status|enabled|
|» events|account.created|
|» events|person.updated|
|» events|account.updated|
|» events|loan.updated|
|» events|loan.created|
|» events|person.created|

> Example responses

> 200 Response

```json
{
  "data": {
    "updated": true
  }
}
```

<h3 id="patch__api_v1_webhook-endpoints_{webhook-id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="patch__api_v1_webhook-endpoints_{webhook-id}-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|object|true|none|none|
|»» updated|boolean|true|none|none|
