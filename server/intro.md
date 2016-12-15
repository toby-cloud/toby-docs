# Toby Server

# NOTE: Server information will be made PRIVATE soon.

### Connecting to the Server

To connect to the Server, a Client must send a CONNECT Packet to the Server. 

The CONNECT Packet must include the following: 
* BotID: The ID of the bot attempting to make the connection.
* BotSk: The secret key of the bot attempting to make the connection.

If the connection is successful, the Server will send a CONNACK Packet. The Client has an OnConnectHandler that will be called when the CONNACK Packet is received.


### Disconnecting from the Server

The Client is disconnected from the Server automatically if a second Client tries to connect to the Server with the same bot credentials. However, if the first Client is programmed to try to reconnect automatically, when it attempts to reconnect it will disconnect the second Client and reconnect to the Server.


