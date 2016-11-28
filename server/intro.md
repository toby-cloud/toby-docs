# Toby Server

## Connecting and Subscribing to Bot Messages

To connect to the Server, a Client must send a CONNECT Packet to the Server. The
CONNECT Packet must include the following:

* Client identifier: the ID of the bot attempting to make the connection.
* User Name: the ID of the bot attempting to make the connection.
* Password: the SK of the bot attempting to make the connection.

Note that the client identifier and username must be the same.
If the connection is successful, the Server will send a CONNACK Packet.


## Receiving messages

Now to receive data from the Server, the bot must send a SUBSCRIBE packet to the
server with the following payload:

* Topic: `client/ID` where ID is the ID of the bot.

If the subscription is successful, the Server will send a SUBACK Packet. Any messages
for the bot will be published to this subscribed topic.

When there is a message for the bot, the Server will send PUBLISH packet to
the bot. The message payload will be a UTF-8 encoded JSON string with the following
fields:

- from: (String) the sender of the message.
- payload: (JSON Object) the message payload.
- tags: (Array) the message tags.
- ack: (String) the tag any response messages should be tagged with.


## Making requests

To make a request, a bot must send an MQTT PUBLISH packet to the server with the
following:

- Topic: `server/<id>/<endpoint>` where `<id>` is the ID of the bot.
- Payload: The UTF-8 encoded JSON string representation of the request.


