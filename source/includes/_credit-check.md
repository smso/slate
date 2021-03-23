# Credit

## Checking remaining credit

```shell

curl --request GET --header 'X-Authorization: smso-api-key' "https://app.smso.ro/api/v1/credit-check"

```

```php
<?php
use GuzzleHttp\Client;

$client = new Client;
$request = $client->request('GET', 'https://app.smso.ro/api/v1/credit-check', [
        'headers' => [
            'X-Authorization' => 'smso-api-key',
        ],
]);

var_dump(json_decode($request->getBody()->getContents()));
```

```javascript
// nothing yet
```

> The above command returns JSON structured like this:

```json
{
  "status" : 200, 
  "credit_value" : 4847.72
}
```

This endpoint returns the remaining credit for the team

### HTTP Request

`GET https://app.smso.ro/api/v1/credit-check`

### Query Parameters

None.
 
