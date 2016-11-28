# Bots

A bot is any device that connects and communicates with Toby.
There are three types of bots:

1. User Bots
2. Standard Bots
3. Socket Bots

### User Bots

User bots serve to manage a user's account and other bots. They are created by signing up. Once created, a user bot can establish a secure MQTT connection with the Toby Broker using its credentials.

A user bot can send messages to any of the bots it manages. It also receives all messages sent by any bot it manages, regardless of tags.

User bots have the following abilities:

* Create bots: a user bot can create standard bots.
* Remove bots: a user bot can remove standard bots in the same account.
* List bots: a user bot can see all other bots in the same account.
* Manage permissions: a user bot can set rules for bots in the same account.
* Send messages: a user bot can send messages to all other bots in the same account.


### Standard Bots

Standard bots are created by user bots, and are the central part of Toby. They sign in using the credentials created by the user bot who created it.

Standard bots have two main functions: send messages, and follow tags. A bot can send a message with tags to Toby. Any bot in the same account that is online and subscribed to a tag in the message will receive that message.

Standard bots have the following abilities:

* Follow tags: a standard bot can follow tags. Any message posted with a tag will be relayed to any online bot following that tag.
* Unfollow tags: a standard bot can unfollow tags.
* View subscriptions: a standard bot can see any tags that it is currently following.
* Send messages: a standard bot can send messages to other bots in the same account.
* Allow webhooks: a standard bot can choose to allow POST requests. When activated, any data posted will be relayed to the bot as a message.
* Create sockets: a standard bot can create socket bots.


### Socket Bots

Socket bots are created by standard bots. They sign in using the credentials given to the standard bot who created it. Unlike standard bots who can send messages to any bot in the same account, socket bots can only send messages to the bot who created it.

Socket bots can be used in many ways, but were primarily designed as a lightweight alternative to WebSockets.

Socket bots has the following ability:

* Send messages: a socket bot can only send messages to the bot who created it. Regardless of the tags in the message, it will only be sent to the host bot.

