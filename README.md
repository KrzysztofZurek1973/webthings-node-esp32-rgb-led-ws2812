# Web Connected RGB Led Line Example

This example shows the usage of RGB led line controller (with WS2812, WS2813) which uses [Web Thing Server](https://github.com/KrzysztofZurek1973/iot_components/tree/master/web_thing_server) on ESP32 (with [esp-idf ver. 4.0](https://github.com/espressif/esp-idf)).

Connection of ESP32 devkit board with WS2813 diode line is shown below. Led's data line is connected to IO23 of ESP32. Led line is powered from devkit and can draw maximum aproximitly about 600mA from the board (it gives only 10 diodes with maximum light). For more diodes external 5VDC current source is necessary and it must be connected directly to the led line.

![connection](./p4.png)

Picture below shows the Gateway Web Interface for this thing.

![rgb line](./p3.png)
	
 The controller has the following properties:
 
- `on` - ON/OFF led line
- `diodes` - number of diodes in the line
- `color` - RGB color defined for some patterns
- `speed` - pattern refreshment speed, 0 .. 100
- `brgh` - leds' brightness, 0 .. 100
- `pattern` - currently running pattern

Patterns list is implemented as `string enum` in json format. Picture below shows that list on Firefox Android.

![patterns](./p2.png)

## Requirements

The following software must be copied into `components` folder:

- [Web Thing Server](https://github.com/KrzysztofZurek1973/iot_components/tree/master/web_thing_server)
- [RGB patterns](https://github.com/KrzysztofZurek1973/RGB_led_line_patterns)
- [ws2812 controller](https://github.com/KrzysztofZurek1973/iot_components/tree/master/thing_ws2812_controller)

## Documentation

By the first power-up the node starts in **AP** mode with SSID: ```iot-node-ap``` and password: ```htqn9Fzv```. After loggin into this WiFi network load the main page by typing in browser ```iot-node-ap.local:8080/``` (it does not work on Android) or ```192.168.4.1:8080/```.

On the page write SSID and password of the WiFi network where the node will work. In the last position enter the local node's name.

Pressing *submit* causes writing data into flash and restart of the node in *station* mode. If you want to change the WiFi SSID or password later just connect ```GPIO27``` to GND, this causes node's restart in **AP** mode as in the previous paragraph.

If *WebThing Gateway* runs in the same WiFi network go to *Things* category on gateway and press *plus* sign. Gateway shoud find new things, press *Save* and *Done*.


### Project Configuration

```
idf.py menuconfig
```

In the *RGB Controller Configuration* menu item ```WS2812 Data GPIO number``` can be set for led data line (default is 23).

### Build and Flash


Build: ```idf.py build```

Flash: ```idf.py flash``` and press boot button.

## Links

* [WebThing Gateway](https://iot.mozilla.org/gateway/) - https://iot.mozilla.org/gateway/
* [Web Thing API](https://iot.mozilla.org/wot/) - https://iot.mozilla.org/wot/
* [esp-idf](https://github.com/espressif/esp-idf) - https://github.com/espressif/esp-idf

## License

This project is licensed under the MIT License.

## Authors

* **Krzysztof Zurek** - [kz](https://github.com/KrzysztofZurek1973)
