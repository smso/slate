# Sending a messages

```shell

curl --request POST --header 'X-Authorization: smso-api-key' "https://app.smso.ro/api/v1/send" \
  -d "sender=1" \
  -d "to=+40722334455" \
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
// nothing yet
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
body              | Yes | Contents of the message
webhook           | No  | Identical to webhook_status, preserved for legacy purposes
webhook_status    | No  | Webhook for receiving the SMS message status
webhook_responses | No  | Webhook for receiving the SMS message reply

<aside class="success">
Remember — check the webhook for the complete detals on the message. [Webhook documentation](#webhooks)
</aside>  

