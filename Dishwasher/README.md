# Dishwasher card for Home Assistant

<img src="https://github.com/kraevski" width="750">

## Installation guide:

1. Install the following third-party tools using [HACS](https://www.hacs.xyz/):
    - [Browser Mod](https://github.com/thomasloven/hass-browser_mod)
    - [Button Card](https://github.com/custom-cards/button-card)
    - [Card Mod](https://github.com/thomasloven/lovelace-card-mod)
    - [Mushroom Cards](https://github.com/piitaya/lovelace-mushroom)
    - [Layout Card](https://github.com/thomasloven/lovelace-layout-card)

2. For devices working with `Home Connect` you can use the [Official integration](https://www.home-assistant.io/integrations/home_connect) or the [Alternative custom integration](https://github.com/ekutner/home-connect-hass).

3. Add the content of the [Card](card_dishwasher.yaml) to your dashboard.

4. Replace all sensors and entities with the ones you have from your Dishwasher integration.

5. Upload the image `dishwasher.jpg` to the `/homeassistant/www/images/` folder. If the folder does not exist, create it. You can use this image of find another. To upload files, you can use the Home Assistant Add-on: [File editor](https://github.com/home-assistant/addons/blob/master/configurator/README.md).
