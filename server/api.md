# API


### SEND

Access: all bots

Topic: `server/<id>/send`

Payload:

- payload: (JSON object) the message payload.
- tags: (Array) the message tags.
- ack: (String) the tag any response messages should be tagged with.

When the Server receives a send request, it will determine the recipients
of the message based on the type of bot making the request, and the message tags.

- If a user bot sends a message, it will be relayed to any of the user's bots
subscribed to a tag in the message.
- If a standard bot sends a message, it will be sent to the user bot, and it will
be relayed to any of the user's bots subscribed to a tag in the message.
- If a socket bot sends a message, it will be relayed to the bot's host, regardless
of tags.


### INFO

Access: all bots

Topic: `server/<id>/info`

Payload:

- ack: (String) the tag included in the server's response message.


### FOLLOW

Access: standard bots only

Topic: `server/<id>/follow`

Payload:

- tags: (Array) the tags to subscribe to
- ack: (String) the tag included in the server's response message.


### UNFOLLOW

Access: standard bots only

Topic: `server/<id>/unfollow`

Payload:

- tags: (Array) the tags to unsubscribe from
- ack: (String) the tag included in the server's response message.


### CREATE BOT

Access: user bots only

Topic: `server/<id>/create-bot`

Payload:

- id: (String) the ID of the new bot
- sk: (String) the SK of the new bot
- ack: (String) the tag included in the server's response message.


### REMOVE BOT

Access: user bots only

Topic: `server/<id>/remove-bot`

Payload:

- id: (String) the ID of the bot to delete
- ack: (String) the tag included in the server's response message.


### CREATE SOCKET

Access: standard bots only

Topic: `server/<id>/create-socket`

Payload:

- persist: (Boolean) if false, bot will be permanently removed on first disconnect
- ack: (String) the tag included in the server's response message.


### REMOVE SOCKET

Access: standard bots only

Topic: `server/<id>/remove-socket`

Payload:

- id: (String) the ID of the socket to delete
- ack: (String) the tag included in the server's response message.


### HOOKS ON

Access: standard bots only

Topic: `server/<id>/hooks-on`

Payload:

- sk: (String) the hook secret
- ack: (String) the tag included in the server's response message.


### HOOKS OFF

Access: standard bots only

Topic: `server/<id>/hooks-off`

Payload:

- ack: (String) the tag included in the server's response message.

