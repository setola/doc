---
title: 'Getting started with MQTT protocol between Arduino and Ubuntu'
date:
draft: true
tags: ['Arduino']
---

## What is it

MQTT it's a machine-to-machine connectivity protocol. It's designed to be as cheap as possible in terms of bandwidth and
power consumption. Usually make some sensors communicate with a bigger computer that chooses what to do with the
sensor's data. My first didactic project that uses MQTT involves Arduino, Ubuntu Server and a normal LAN connection. I
have an Arduino with an Ethernet shield connected to my LAN and i want to switch the pin 13 led by subscribing a MQTT
topic from a browser or a smartphone.

## How it works

The communication process is split into two parts:

* a publisher pushes a data to a broker's topic
* the broker propagates the data to all the subscribers of that topic

![mqtt](/howto/arduino/getting-started-with-mqtt-protocol-between-arduino-and-ubuntu/mqtt.jpg)

## Install broker on Ubuntu Server

The broker (usually named server) implementation I've choosed is Mosquitto. Installing it super easy:

```bash
sudo apt-get install mosquitto
```

and you are ready to go. To test it's working you can connect you preferred client to the Ubuntu Server's ip on port
1883, which is the standard one for MQTT

## Installing client library for Arduino IDE

I've chosen this implementation for Arduino 1.0.3: https://github.com/knolleary/pubsubclient Go to you Arduino
installation folder and move to `libraries` folder. If you have git on your system you can clone the repository and
copy the content of https://github.com/knolleary/pubsubclient/tree/master/PubSubClient into
your `arduino-installation-folder/libraries/`

## Basic testing sketch

TODO

## Resources

1. [http://mqtt.org](http://mqtt.org "MQTT website") home of the MQTT project
2. [http://mqtt.io/](http://mqtt.io/ "MQTT IO project") the quickest way to have a demo client up and running to play
   with MQTT: it's web-based so all you need is your browser!
3. [http://mosquitto.org](http://mosquitto.org "Moquitto website") multi-platform C broker (server) implementation of
   MQTT
4. [http://mobilave.info/blog/2012/Quick\_start\_guide\_for\_the\_Eclipse\_Paho\_Plug-in.html](http://mobilave.info/blog/2012/Quick_start_guide_for_the_Eclipse_Paho_Plug-in.html "Installing Eclipse PAHO")
   the not-easy guide to installation of Paho view plugin for eclipse
5. [http://knolleary.net/arduino-client-for-mqtt/](http://knolleary.net/arduino-client-for-mqtt/ "Arduino client for MQTT protocol")
   Arduino client for MQTT
