# Security Protocols

### Database Security

* Use [BCrypt](https://github.com/kelektiv/node.bcrypt.js) to encrypt hash user passwords and keys.
* BCrypt is a widely accepted encryption library for Node.

### Network Security

* Use TLS to secure the connection. See [Hive MQTT Docs](http://www.hivemq.com/blog/mqtt-security-fundamentals-tls-ssl). 
* TODO: Conduct load testing for constrained clients to ensure the additional TLS does not affect efficiency.

### Message Security

* End-to-end payload encryption using asymmetric RSA with 2048-bit length keys.
* Each bot will have RSA public and private keys. Upon connecting, the bot will send its RSA public key to its master bot, and receive the public RSA key of its master bot.
* All messages are encrypted using the recipient's public key, and only the recipient can decrypt it using its private key.
* TODO: Conduct load testing for large messages, such as images.

 