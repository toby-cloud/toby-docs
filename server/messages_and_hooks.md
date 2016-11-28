# Messages and Hooks

### Messages

Messages are sent by bots and have the following components:

* Body: the main message payload.
* Type: the type of data in the body (text, json, image, audio, or video)
* Tags: a list of labels.
* Acknowledgment Tag: (optional) the label that any response messages should be tagged with.

Any messages sent with one or more tags will be relayed to any bots subscribed to one or more of those tags. So, to send a message from Bot A to Bot B, you could have Bot B subscribe to #botB, then Bot A can send a message tagged with #botB. Bot B will receive that message instantly.


### Hooks

Any standard bot can activate webhooks by providing a secret token to the server. Once activated, any POST requests to the given url with a matching token will be relayed to the bot.

