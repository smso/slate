# Webhooks

## Message status

```shell

# use this command to emulate a webhopok

curl --request POST "https://your-server.com/webhooks/smso" \
  -d "uuid=aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee" \
  -d "status=sent" \
  -d "sent_at=2019-05-01 12:30:09" \
  -d "delivered_at=2019-05-01 12:20:09" \
  -d "receiver['number']=+40722334455" \
  -d "receiver['mcc']=226" \
  -d "receiver['mnc']=03"
  
```

```php

```

```javascript
// soon 
```

> The above command returns JSON structured like this:

```json

```

This is an endpoint on your application side that handles the status of the message.

### HTTP Request

`POST https://your-server.com/webhooks/smso`

<aside class="notice">
Remember that webhooks can be set up either in your team's account or per message sent.
</aside>  
 

### Query Parameters


Parameter           | Can be empty? | Description
---------           | ------- | -----------
uuid                | No | Uuid received from sending the message
status              | No | Message status
sent_at             | No | Time sent to the network
delivered_at        | Yes| Time delivered to phone
receiver['number']  | No | Receiving number in E.164 Format.	
receiver['mcc']     | No | Mobile Country Code
receiver['mnc']     | No | Mobile Network Code

<aside class="success">
Remember: All dates are in UTC. 
</aside>


## Receiving messages

```shell

# use this command to emulate a webhopok

curl --request POST "https://your-server.com/webhooks/smso" \
  -d "body=aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee" \
  -d "replied_to=sent" \
  -d "received_at=2019-05-01 12:30:09" \
  -d "sender['number']=+40722334455" \
  -d "sender['mcc']=226" \
  -d "sender['mnc']=03"
  
```

```php
// soon 

```

```javascript
// soon 
```

> The above command returns JSON structured like this:

```json

```

This is an endpoint on your application side that handles receiving messages.

### HTTP Request

`POST https://your-server.com/webhooks/smso`

<aside class="notice">
Remember that webhooks can be set up either in your team's account or per message sent.
</aside>  
 

### Query Parameters


Parameter           | Can be empty? | Description
---------           | ------- | -----------
body                | No | Contents of the message
replied_to          | Yes | Uuid of the message that the number received and is now responding to
received_at         | No | Time the message was received
sender['number']    | No | Sender number in E.164 Format.	
sender['mcc']       | No | Mobile Country Code
sender['mnc']       | No | Mobile Network Code

<aside class="success">
Remember: All dates are in UTC. 
</aside>
  

