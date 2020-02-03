# Web Connected RGB Controller Example (WS2812, WS2813)

RGB led line controller which uses [Web Thing Server](https://github.com/KrzysztofZurek1973/iot_components/tree/master/web_thing_server) on ESP32 (with [esp-idf ver. 4.0](https://github.com/espressif/esp-idf)).

Picture below shows the Gateway Web Interface of the thing.

![rgb line](./p1.png)
	
 Controller has the following properties:
 
- `on` - ON/OFF led line
- `diodes` - number of diodes in the line
- `pattern` - currently running pattern
- `color` - RGB color defined for some patterns
- `speed` - pattern refreshment speed, 0 .. 100
- `brgh` - leds' brightness, 0 .. 100

## Requirements

The following software must be copied into `components` folder:

- [Web Thing Server](https://github.com/KrzysztofZurek1973/iot_components/tree/master/web_thing_server)
- [RGB patterns](https://github.com/KrzysztofZurek1973/RGB_led_line_patterns)
- [ws2812 controller](https://github.com/KrzysztofZurek1973/iot_components/tree/master/thing_ws2812_controller)

## Documentation

TODO


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
