# Send A SMS message

## Sending a message

```shell

curl --request POST --header 'x-authorization: smso-api-key' "https://app.smso.ro/api/v1/send" \
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
to                | Yes | E.164 Format. The + is optional	
sender            | Yes | The ID of the sender
body              | Yes | 
webhook_status    | No | Webhook for receiving the SMS message status
webhook_received  | No | Webhook for receiving the SMS message reply

<aside class="success">
Remember — check the webhook for the complete detals on the message.
</aside>  

