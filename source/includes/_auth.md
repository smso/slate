# Authentication

> To authorize, use this code:


```shell
# With shell, you can just pass the correct header with each request
curl -H "X-Authorization: API-KEY"  "https://app.smso.ro/api/v1/" 

# full example as query string
curl "https://app.smso.ro/api/v1/send?sender=4&to=0722334455&body=Message%20Body&apiKey=API-KEY"

```

```php
<?php

// via file_get_contents
$opts = [
    "http" => [
        "method" => "POST",
        "header" => "X-Authorization: API-KEY"
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
        'X-Authorization' => 'API-KEY',
    ],
]);

var_dump(json_decode($request->getBody()->getContents()));

```

```javascript
// soon
```

> Make sure to replace `API-KEY` with your Tean's API key from our [developer page](https://app.smso.ro/developers/api).

SMSO uses API keys to allow access to the API. You can register a new SMSO API key at our [developer page](https://app.smso.ro/developers/api).

SMSO expects for the API key to be included in all API requests to the server in a header that looks like the following:

1. Via a header: `X-Authorization: API-KEY`
2. Via a query string, either POST OR GET, just append it to the URL like *&apiKey=API-KEY*



<aside class="notice">
You must replace <code>API-KEY</code> with your personal API key.
</aside>
