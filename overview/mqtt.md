## MQTT Protocol

[MQTT](http://mqtt.org/) is a lightweight, machine-to-machine connectivity publish/subscribe protocol. Because of its small code footprint, and its ability to support wireless networks with varying levels of latency, it is becoming extremely popular for IoT and other real-world applications.  

Toby abstracts the process of creating an MQTT connection between your devices. It uses MQTT 3.1.

#### [MQTT Terminology](http://docs.oasis-open.org/mqtt/mqtt/v3.1.1/os/mqtt-v3.1.1-os.pdf)
* MQTT Message
    * The data carried by the MQTT protocol across the network for the application. 
    * Messages have an associated Quality of Service and a Topic Name.
* Client
    * A program or device that uses MQTT. A Client always establishes the Network Connection to the Server and supports the following methods.
    * Publish Messages that other Clients might be interested in.
    * Subscribe to request Messages that it is interested in receiving.
    * Unsubscribe to remove a request for Messages.
    * Disconnect from the Server.
* Server
    * A program or device that acts as an intermediary between Clients which publish Messages and Clients which have made Subscriptions. 
    * Accepts Network Connections from Clients.
    * Accepts Messages published by Clients.
    * Processes Subscribe and Unsubscribe requests from Clients.
    * Forwards Messages that match Client Subscriptions.
* Subscription
    * A Subscription comprises a Topic Filter and a maximum QoS. 
    * A Subscription is associated with a single Session. A Session can contain more than one Subscription.
    * Each Subscription within a session has a different Topic Filter.
* Topic Name
    * The label attached to a Message which is matched against the Subscriptions known to the
Server. The Server sends a copy of the Message to each Client that has a matching Subscription.
* Topic Filter
    * An expression contained in a Subscription, to indicate an interest in one or more topics.
    * A Topic Filter can include wildcard characters.
* Session
    * A stateful interaction between a Client and a Server. Some Sessions last only as long as the Network Connection ("non-persistent"), others can span multiple consecutive Network Connections between a Client and a Server ("persistent").

