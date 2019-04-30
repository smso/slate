# Authentication

> To authorize, use this code:


```shell
# With shell, you can just pass the correct header with each request
curl -H "X-Authorization: smso-api-key"  "https://app.smso.ro/api/v1/" 
```

```php
<?php

// via file_get_contents
$opts = [
    "http" => [
        "method" => "POST",
        "header" => "X-Authorization: smso-api-key"
    ]
];

$context = stream_context_create($opts);

$content = file_get_contents('https://app.smso.ro/api/v1/', false, $context);

var_dump($content);

// via guzzle
use GuzzleHttp\Client;

$client = new Client;
$request =  $client->request('GET', 'https://app.smso.ro/api/v1/', [
    'headers' => [
        'X-Authorization' => 'nece',
    ],
]);

var_dump(json_decode($request->getBody()->getContents()));

```

```javascript
// soon
```

> Make sure to replace `API-KEY` with your API key.

SMSO uses API keys to allow access to the API. You can register a new SMSO API key at our [developer page](https://app.smso.ro/developers/api).

SMSO expects for the API key to be included in all API requests to the server in a header that looks like the following:

`X-Authorization: smso-api-key`

<aside class="notice">
You must replace <code>API-KEY</code> with your personal API key.
</aside>
