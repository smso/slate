# Send A SMS message

## Sending a message

```shell

curl --request POST --header 'x-authorization: nece' "https://app.smso.ro/api/v1/send" \
  -d "sender=1" \
  -d "to=40726459188" \
  -d "body=Testing"
     
  
```

```php
<?php
use GuzzleHttp\Client;

$client = new Client;
$request = $client->request('POST', 'https://app.smso.ro/api/v1/send', [
        'headers' => [
            'X-Authorization' => 'smso-api-key',
        ],
       'form_params' => [
           'to' => '',
           'body' => '',
           'sender' => '',
       ],
]);

var_dump(json_decode($request->getBody()->getContents()));
```

```javascript
// soon 
```

> The above command returns JSON structured like this:

```json
{
  "status": 200,
  "responseToken": "aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee"
}
```

This endpoint sends an SMS Message

### HTTP Request

`POST https://app.smso.ro/api/v1/send`

### Query Parameters

Parameter | Required? | Description
--------- | ------- | -----------
to | Yes | 
sender | Yes | The ID of the sender
body | Yes | 
webhook_status | No | Webhook for receiving the SMS message status
webhook_received | No | Webhook for receiving the SMS message reply

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


