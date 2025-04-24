# Day/Night switch button for Home Assistant

<img src="https://github.com/kraevski" width="750">

## Installation

1. Third party tools we need to install using [HACS](https://www.hacs.xyz/)
- [Mushroom Cards](https://github.com/piitaya/lovelace-mushroom)
- [Card Mod](https://github.com/thomasloven/lovelace-card-mod)
2. Add the content of the [Script file](script_day_and_night_switch.yaml) to your scripts.yaml or by using Settings -> Automations & scenes -> Scripts -> Create automation
3. Configure your lights entites however you like using *light.turn_on* and *light_turn_off* actions and utilising the data properties like *brightness_pct*
4. Upload _day.png_ and _night.png_ to _/homeassistant/www/images/_ folder (if it does not exist, you should create it). Uploading files can be done by using the Home Assistant Add-on: [File editor](https://github.com/home-assistant/addons/blob/master/configurator/README.md)
5. Add the content of the [Card](card_day_night_switch.yaml) to your dashboard