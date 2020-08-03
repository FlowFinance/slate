# Pre-qualify

## Eligibility for a credit line

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1/pre-qualify \
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

r = requests.post('/api/v1/pre-qualify', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "cnpj": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'authorization':'string'
};

fetch('/api/v1/pre-qualify',
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

`POST /api/v1/pre-qualify`

*This endpoint returns whether a business entity is eligible for applying for an account.*

> Body parameter

```json
{
  "cnpj": "string"
}
```

<h3 id="post__api_v1_pre-qualify-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|body|body|object|true|none|
|» cnpj|body|string|true|none|

> Example responses

> 200 Response

```json
{
  "data": {
    "cnpj": "string",
    "eligible": true
  }
}
```

<h3 id="post__api_v1_pre-qualify-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="post__api_v1_pre-qualify-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|object|true|none|none|
|»» cnpj|string|true|none|none|
|»» eligible|boolean|true|none|none|

<aside class="success">
This operation does not require authentication
</aside>
