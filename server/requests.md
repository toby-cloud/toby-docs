# Requests


### Receiving messages

Now to receive data from the Server, the bot must send a SUBSCRIBE packet to the
server with the following payload:

* Topic: `client/<botId>`

If the subscription is successful, the Server will send a SUBACK Packet. Any messages
for the bot will be published to this subscribed topic.

When there is a message for the bot, the Server will send PUBLISH packet to
the bot. The message payload will be a UTF-8 encoded JSON string.
* `from`: (String) The botId of sender of the message.
* `payload`: (JSON Object) The message payload.
* `tags`: (Array) The message tags.
* `ack`: (String) The tag any response messages should be tagged with.


## Making requests

To make a request, a bot must send a MQTT PUBLISH packet to the server with the
following:

* Topic: `server/<botId>/<endpoint>`
* Payload: The UTF-8 encoded JSON string representation of the request.




