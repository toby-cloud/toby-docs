# Bots

A bot is any device that connects and communicates with Toby.
There are three types of bots:

1. User Bots
2. Standard Bots
3. Socket Bots

These bots have a master-slave relationship of unidirectional control. The User bot is a master to its Standard bot slaves, which is a master to its Socket bot slaves.

### User Bots

User bots serve to manage a user's account and its slave bots. These are created when a new user signs up. Once created, a User bot can establish a secure MQTT connection with the Toby Broker using its credentials.

A User bot can send messages to any of the slave bots it manages. It also receives all messages sent by any bot it manages, regardless of tags.

User bots have the following abilities:

* Create bots: A User bot can create Standard bots.
* Remove bots: A User bot can remove Standard bots that it owns.
* List bots: List all Standard bot slaves owned by the User bot. Note: In the future, this will support listing all Socket bots owned by each Standard bot.
* Manage permissions: A User bot can set rules for bots that it owns.
* Send messages: A User bot can send messages to any or all bots that it owns.


### Standard Bots

Standard bots are created by User bots, and are the central part of Toby. They sign in using the credentials created by the User bot who created them.

Standard bots have two main functions: send messages, and follow tags. A bot can send a message with tags to Toby. Any bot in the same account that is online and subscribed to a tag in the message will receive that message.

Standard bots have the following abilities:

* Follow tags: A Standard bot can follow tags. Any message posted with a tag will be relayed to any online bot following that tag.
* Unfollow tags: A Standard bot can unfollow tags.
* View subscriptions: A Standard bot can see any tags that it is currently following.
* Send messages: A Standard bot can send messages to other bots in the same account.
* Allow webhooks: A Standard bot can choose to allow POST requests. When activated, any data posted will be relayed to the bot as a message.
* Create sockets: A Standard bot can create Socket bots.


### Socket Bots

Socket bots are created by Standard bots. They sign in using the credentials given to the standard bot who created them. Unlike Standard bots who can send messages to any bot in the same account, Socket bots can only send messages to the Standard bot that created it.

Socket bots can be used in many ways, but were primarily designed as a lightweight alternative to WebSockets.

Socket bots have the following ability:

* Send messages: A Socket bot can only send messages to the bot that created it. Regardless of the tags in the message, it will only be sent to its master bot.

