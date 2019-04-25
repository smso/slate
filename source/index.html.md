---
title: SMSO Api Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - php


toc_footers:
  - <a href='https://app.smso.ro/'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the SMSO API! You can use our API to access SMSO API endpoints.

We have language bindings in Shell, PHP, JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:


```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "X-Authorization: API-KEY"
```

```php
<?php

// via file_get_contents
$opts = [
    "http" => [
        "method" => "POST",
        "header" => "X-Authorization: API_KEY"
    ]
];

$context = stream_context_create($opts);

$content = file_get_contents('https://app.smso.ro/api/v1/senders', false, $context);

var_dump($content);

// via guzzle
use GuzzleHttp\Client;

$client = new Client;
$client->request('POST', 'https://app.smso.ro/api/v1/senders', [
        'headers' => [
            'X-Authorization' => 'API_KEY',
        ],
        'form_params' => [],
    ]);


```


> Make sure to replace `API-KEY` with your API key.

SMSO uses API keys to allow access to the API. You can register a new SMSO API key at our [developer portal](https://app.smso.ro/developers/api).

SMSO expects for the API key to be included in all API requests to the server in a header that looks like the following:

`X-Authorization: API-KEY`

<aside class="notice">
You must replace <code>API-KEY</code> with your personal API key.
</aside>

# Sendes

## Get All Senders available

```curl

```

```php
<?php
use GuzzleHttp\Client;

$client = new Client;
$client->request('POST', 'https://app.smso.ro/api/v1/senders', [
        'headers' => [
            'X-Authorization' => 'API_KEY',
        ],
        'form_params' => [
            'body' => $message->body,
            'receiver' => $number,
            'uuid' => $message->uuid,
            'priority' => $priority,
            'network' => $network,
            'sender' => $customSender,
        ],
    ]);

```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = SMSO::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = SMSO::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

