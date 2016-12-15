# API

### SEND

Access: all bots

Topic: `server/<botId>/send`

Payload:

* `payload`: (JSON object) The message payload.
* `tags`: (Array) The message tags.
* `ack`: (String) The tag any response messages should be tagged with.

When the Server receives a SEND request, it will determine the recipients
of the message based on the type of bot making the request, and the message tags.

* If a user bot sends a message, it will be relayed to any of the user's bots
subscribed to a tag in the message.
* If a standard bot sends a message, it will be sent to the user bot, and it will
be relayed to any of the user's bots subscribed to a tag in the message.
* If a socket bot sends a message, it will be relayed to the bot's host, regardless
of tags.


### INFO

Access: all bots

Topic: `server/<id>/info`

Payload:

- `ack`: (String) The tag included in the server's response message.

When the server receives an INFO request, the response is different depending on the bot type.
* User bot: The bot's type (User), botId, and a list of the Standard bots it owns and the INFO for each of them.
* Standard bot: The bot's type (Standard), botId, subscriptions, and whether or not it is a hook. Note: This will later support listing its Socket bots.
* Socket bot: The bot's type (Socket) and botId.


### FOLLOW

Access: standard bots only

Topic: `server/<id>/follow`

Payload:

- `tags`: (Array) The tags to subscribe to.
- `ack`: (String) The tag included in the server's response message.


### UNFOLLOW

Access: standard bots only

Topic: `server/<id>/unfollow`

Payload:

- `tags`: (Array) The tags to unsubscribe from.
- `ack`: (String) The tag included in the server's response message.


### CREATE BOT

Access: User bots only

Topic: `server/<id>/create-bot`

Payload:

- `botId`: (String) The botID of the new bot
- `botSk`: (String) The secret key of the new bot
- `ack`: (String) The tag included in the server's response message.


### REMOVE BOT

Access: User bots only

Topic: `server/<id>/remove-bot`

Payload:

- `botId`: (String) The botID of the bot to delete.
- `ack`: (String) The tag included in the server's response message.


### CREATE SOCKET

Access: Standard bots only

Topic: `server/<id>/create-socket`

Payload:

- `persist`: (Boolean) If false, bot will be permanently removed on first disconnect. If true, bot will automatically try to reconnect if disconnected.
- `ack`: (String) The tag included in the server's response message.


### REMOVE SOCKET

Access: Standard bots only

Topic: `server/<id>/remove-socket`

Payload:

- `botId`: (String) The botID of the Socket bot to delete.
- `ack`: (String) The tag included in the server's response message.


### HOOKS ON

Access: Standard bots only

Topic: `server/<id>/hooks-on`

Payload:

- `sk`: (String) The hook secret.
- `ack`: (String) the tag included in the server's response message.


### HOOKS OFF

Access: Standard bots only

Topic: `server/<id>/hooks-off`

Payload:

- `ack`: (String) The tag included in the server's response message.

