# Messages

## Sending a message

```shell

curl --request POST --header 'X-Authorization: smso-api-key' "https://app.smso.ro/api/v1/send" \
  -d "sender=1" \
  -d "to=+40722334455" \
  -d "body=Testing"s

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

## Sending a message via SIM

```shell

curl --request POST --header 'X-Authorization: smso-api-key' "https://app.smso.ro/api/v1/send/sim \
  -d "to=+40722334455" \
  -d "body=Testing"s

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

This endpoint sends an SMS Message with the predefined sender of SIM

### HTTP Request

`POST https://app.smso.ro/api/v1/send/sim`

### Query Parameters

Parameter | Required? | Description
--------- | ------- | -----------
to                | Yes | E.164 Format. The + is optional	
body              | Yes | Contents of the message
webhook           | No  | Identical to webhook_status, preserved for legacy purposes
webhook_status    | No  | Webhook for receiving the SMS message status
webhook_responses | No  | Webhook for receiving the SMS message reply

<aside class="success">
Remember — check the webhook for the complete detals on the message. [Webhook documentation](#webhooks)
</aside>  

## Checking the message status

```shell

curl --request POST "https://app.smso.ro/api/v1/status" \
  -d "responseToken=aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee"

// also GET  
curl "https://app.smso.ro/api/v1/status?responseToken=aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee"
```

```php
<?php
use GuzzleHttp\Client;s

$client = new Client;

$request = $client->request('GET', 'https://app.smso.ro/api/v1/status?responseToken=aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee');
// also POST  
$request = $client->request('POST', 'https://app.smso.ro/api/v1/status', [
          'form_params' => [
              'responseToken' => 'aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee',
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
    "data": {
        "status": "delivered",
        "sent_at": "2019-05-1 15:18:20",
        "delivered_at": "2019-05-1 15:18:25",
        "receiver": {
            "number": "+40722334455",
            "mcc": "226",
            "mnc": "01"
        }
    }
}
```

This endpoint sends an SMS Message

### HTTP Request

`POST or GET https://app.smso.ro/api/v1/status`

### Query Parameters

Parameter | Required? | Description
--------- | ------- | -----------
responseToken | Yes | The uuid from the SEND 


<aside class="notice">
No authentifications is required for checking the status.
</aside>  
