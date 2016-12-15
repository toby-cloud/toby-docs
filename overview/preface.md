# Overview

## Toby MQTT Server

Toby is a simple but powerful application that gives you the ability to create lightning-fast, multi-directional communication channels between all your internet connected devices. It is built using [MQTT](http://mqtt.org/faq), a lightweight network protocol, designed to be used in constrained devices on unreliable networks. The Toby server is live [here](http://toby.cloud) and the clients are explained in the next section.

## Toby-Cloud Clients

Toby-Cloud is a suite of Toby clients at its [github page](https://github.com/toby-cloud). Toby works on anything that can establish an MQTT connection. This means it can work on virtually any device, including Arduinos, Raspberry Pis, smart phones, and browsers. Toby has client libraries available in all major languages that support MQTT, and we are in the process of creating more.

## Example: Ekho

[Ekho](http://ekho.io) is an application that harnesses Toby's power in an unconventional IoT setting - between a mobile phone and a laptop. This is an example application using Toby's websockets client on the desktop or in a browser, Toby's Android client on the mobile device, and Toby's Go client in Ekho's backend server.

