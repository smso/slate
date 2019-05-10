# Check the message status

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
