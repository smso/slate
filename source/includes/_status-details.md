# Message Statuses

```shell
// nothing
```

```php
// nothing
```

```javascript
// nothing
```

> The above command returns JSON structured like this:

```json
// nothing
```

Message status description 

The message can take a number of states.

### Status Descriptions

Status | Final | Description
--------- | ------- | -----------
dispatched | No | The message is in the process of sending to the network. (rarely seen)
sent | No | The message has been sent to the network.
delivered | Yes | The message has been delivered to the phone.
undelivered | Yes | The message was undelivered.
expired | Yes | The message is expired. 
error | Yes | There was an error sending the message.

<aside class="notice">
Keep in mind, if you get a final status, you can discad other updates.  
</aside>  


