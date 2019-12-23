# Senders

## Get the list of available senders

```curl

curl -H "X-Authorization: API-KEY"  "https://app.smso.ro/api/v1/senders" 

```

```php
<?php
use GuzzleHttp\Client;

$client = new Client;
$request = $client->request('GET', 'https://app.smso.ro/api/v1/senders', [
        'headers' => [
            'X-Authorization' => 'API-KEY',
        ],
    ]);
```

```javascript
// nothing yet 
```

> The above command returns JSON structured like this:

```json
[
   {  
     "id":2,
     "name":"Notify",
     "pricePerMessage":3
    },
   {
      "id":4,
      "name":"1847",
      "pricePerMessage":3
   },
   {
      "id":36,
      "name":"0722334455",
      "pricePerMessage":2
   },
   ...
]
```

This endpoint retrieves all the available senders in the the team.

### HTTP Request

`GET https://app.smso.ro/api/v1/senders`

### Query Parameters

None

<aside class="success">
Remember — a happy request is an authenticated request!
</aside>  
