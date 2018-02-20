# esp2mqtt
esp8266 / esp32 mqtt sensor node framework

# Software
- consists of server side tool to
    - manage devices / configurations
    - build firmware for each device
    - manage update needs
    - send OTA firmware updates
- and tiny foodprint config app that wastes as little as possible resources for
    - WIFI setup
    - MQTT setup
    - OTA setup
    - retrieval / flashing of actual app via OTA
- and the actual device specific firmware
    - focus on sensor node type activities
    - follows the mqtt-smarthome architecture
    - does not know how to do OTA but only how to boot into the config app

# Hardware
- focus on esp8266 / esp8252 / esp32 devices
- ability to run on a series of different devices down to 1Mb (256KB) esp01
- config of the device is stored on the device as well as on the server for fault tolerance

# Workflow
- connect device to PC via RS232
- connect to server
- open new device wizard
- select hardware type
- build config app for the hardware type
- configure device specifics (name, connected sensors etc.)
- build actual app for the hardware type and configuration
- flash config app (ideally through browser granted RE232 access?)
- flash actual app through OTA
