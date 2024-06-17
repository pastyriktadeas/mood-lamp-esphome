## Kód pro ESP8266

```
esphome:
  name: esphome-web-f69416
  friendly_name: moodlamp

esp8266:
  board: esp01_1m

# Enable logging
logger:

# Enable Home Assistant API
api:
  encryption:
    key: "MxPSeQGk3zdj71hwzQSn76WVrXw0WIHb4Gm1aPMfAaY="

ota:


wifi:
  ssid: !secret wifi_ssid
  password: !secret wifi_password

  # Enable fallback hotspot (captive portal) in case wifi connection fails
  ap:
    ssid: "Esphome-Web-F69416"
    password: "eF28YvixDNud"

captive_portal:

sensor:
  - platform: dht
    pin: GPIO14
    temperature:
      name: "Teplota"
    humidity:
      name: "Vlhkost vzduchu"
    update_interval: 60s

light:
  - platform: neopixelbus
    type: RGB
    variant: ws2812
    pin: GPIO2
    num_leds: 30
    name: "NeoPixel Light"
```   