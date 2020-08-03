# Loan Preview

## Preview loan offers

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1/loan-preview \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'authorization: string' \
  -H 'account-id: 0' \
  -H 'beneficiary-id: string'

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'authorization': 'string',
  'account-id': '0',
  'beneficiary-id': 'string'
}

r = requests.post('/api/v1/loan-preview', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "amount": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'authorization':'string',
  'account-id':'0',
  'beneficiary-id':'string'
};

fetch('/api/v1/loan-preview',
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

`POST /api/v1/loan-preview`

*Prior to submitting the loan application, submit the prospective loan to a preview API call.*

> Body parameter

```json
{
  "amount": 0
}
```

<h3 id="post__api_v1_loan-preview-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|authorization|header|string|true|none|
|account-id|header|integer(int32)|true|none|
|beneficiary-id|header|string|false|none|
|body|body|object|true|none|
|» amount|body|number(double)|true|none|

> Example responses

> 200 Response

```json
{
  "data": [
    {
      "amount": 0,
      "interest_rate": 0,
      "term": 0,
      "total_debt": 0,
      "installment_amount": 0,
      "offer_token": "string"
    }
  ]
}
```

<h3 id="post__api_v1_loan-preview-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="post__api_v1_loan-preview-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|[object]|true|none|none|
|»» amount|number(double)|true|none|none|
|»» interest_rate|number(double)|true|none|none|
|»» term|integer(int32)|true|none|none|
|»» total_debt|number(double)|true|none|none|
|»» installment_amount|number(double)|true|none|none|
|»» offer_token|string|true|none|none|

