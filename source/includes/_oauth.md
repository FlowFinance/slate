# OAuth

We use a modified OAuth2, Grant Type ["Refresh Token"](https://oauth.net/2/grant-types/refresh-token/) for authentication.

Two types of JWT tokens can be generated: client and account.

Client tokens refer to your platform tokens; they have full permissions on every API endpoint and are able to perform account creation/deletion and operations on behalf of any account.

<aside class="warning">
    You should keep these tokens in your backend only and never share with mobile or web devices.
</aside>

Account tokens have account-specific permissions; they cannot create/delete accounts and can only operate within the bounds of the account for which they were created. If you need to ship credentials to mobile or web devices, this should be used.

## Perform Login


> Code samples

```shell
# You can also use wget
curl -X POST /api/v1/oauth/login \
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

r = requests.post('/api/v1/oauth/login', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'authorization':'string',
  'account-id':'0'
};

fetch('/api/v1/oauth/login',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /api/v1/oauth/login`

*Generate token pair given username and password in the '`Authorization`' header.*

Authorization header expects '`Basic client_id:client_secret`' where the string `client_id:client_secret` is your client_id and your client_secret base64 encoded.

<aside class="notice">
Optionally, you may include the header param account-id in which case account-specific tokens will be generated.
</aside>

<aside class="notice">
Note that refresh-tokens are re-generated on every call and access-tokens are valid for 90 minutes.
</aside>

<h3 id="post__api_v1_oauth_login-parameters">Parameters</h3>

|Name|In|Type|Required|
|---|---|---|---|
|authorization|header|string|true|
|account-id|header|integer(int32)|false|

> Example responses

> 200 Response

```json
{
  "data": {
    "access_token": "string",
    "token_type": "string",
    "expires_in": 0,
    "refresh_token": "string"
  }
}
```

<h3 id="post__api_v1_oauth_login-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="post__api_v1_oauth_login-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|object|true|none|none|
|»» access_token|string|true|none|none|
|»» token_type|string|true|none|none|
|»» expires_in|integer(int32)|true|none|none|
|»» refresh_token|string|true|none|none|

## Refresh an Access Token

`POST /api/v1/oauth/token`

*Refresh access-token given a refresh-token.*

Refresh an expired access-token with a refresh-token.

<aside class="notice">
Optionally, you may include the header param `account-id` in which case account-specific tokens will be generated.
</aside>

<aside class="warning">
Note that refresh-token are NOT re-generated.
</aside>

> Body parameter

```json
{
  "refresh_token": "string"
}
```

<h3 id="post__api_v1_oauth_token-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|account-id|header|integer(int32)|false|none|
|body|body|object|true|none|
|» refresh_token|body|string|true|none|

> Example responses

> 200 Response

```json
{
  "data": {
    "access_token": "string",
    "token_type": "string",
    "expires_in": 0,
    "refresh_token": "string"
  }
}
```

<h3 id="post__api_v1_oauth_token-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="post__api_v1_oauth_token-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|object|true|none|none|
|»» access_token|string|true|none|none|
|»» token_type|string|true|none|none|
|»» expires_in|integer(int32)|true|none|none|
|»» refresh_token|string|true|none|none|
