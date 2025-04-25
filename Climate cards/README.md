# Climate control cards for Home Assistant

<img src="https://github.com/user-attachments/assets/413c74bd-b94c-4a16-a209-91578f4573b4" width="750">

## Installation guide:

1. Install the following third-party tools using [HACS](https://www.hacs.xyz/):
    - [Bubble Card](https://github.com/Cyberjunky/Home-Assistant-Lovelace-Bubble-Card)
    - [Card Mod](https://github.com/thomasloven/lovelace-card-mod)
    - [Mushroom Cards](https://github.com/piitaya/lovelace-mushroom)
    - [Vertical Stack-In Card](https://github.com/ofekashery/vertical-stack-in-card)

2. Add the content of the [Climate Control Card](card_climate_control.yaml) to your dashboard.

3. Add the content of the [Climate Popup Card](card_climate_popup.yaml) to your dashboard. This card will only be visible when you click *Edit dashboard*.

4. Ensure the value of `navigation_path:` in the `tap_action:` of the Climate Control Card matches the value of `hash:` in the Climate Popup Card.

5. Upload the images `kids_room.jpg`, `living_room.jpg`, and `bedroom.jpg` to the `/homeassistant/www/images/` folder. If the folder does not exist, create it. You can use these images, find others or replace them with real pictures of your rooms. To upload files, you can use the Home Assistant Add-on: [File editor](https://github.com/home-assistant/addons/blob/master/configurator/README.md).
