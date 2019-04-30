# Senders

## Get The Available Senders

```curl
curl -H "X-Authorization: smso-api-key"  "https://app.smso.ro/api/v1/senders" 
```

```php
<?php
use GuzzleHttp\Client;

$client = new Client;
$request = $client->request('GET', 'https://app.smso.ro/api/v1/senders', [
        'headers' => [
            'X-Authorization' => 'smso-api-key',
        ],
    ]);
```

```javascript
// soon 
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


