# Robot Vacuum card for Home Assistant

<img src="https://github.com/user-attachments/assets/a2f0d74d-dde1-4de5-b0f8-3cb3718bf9db" />
<img src="https://github.com/user-attachments/assets/fd291016-565d-4034-91ba-168adb7207eb" width="600">

A card for Home Assistant that provides dynamic controls and status feedback for your robot vacuum. The card displays the map of the home and dynamically updates the cleaned area. It shows current status, errors/notifications from the Dock or the Vacuum, gives the option to change Mop Intensity, Mop Mode, Fan Speed. It also displays how many hours until sensors/brushes need to be cleaned and the when the Last Cleaning was and how much time it took. 
Also a conditional card that is visible when the Robot is cleaning.

## Installation guide:

1. Install the following third-party tools using [HACS](https://www.hacs.xyz/):
    - [Browser Mod](https://github.com/thomasloven/hass-browser_mod)
    - [Button Card](https://github.com/custom-cards/button-card)
    - [Card Mod](https://github.com/thomasloven/lovelace-card-mod)
    - [Layout Card](https://github.com/thomasloven/lovelace-layout-card)
    - [Mushroom Select Card](https://github.com/piitaya/lovelace-mushroom/blob/main/docs/cards/select.md)
    - [Mushroom Template Card](https://github.com/piitaya/lovelace-mushroom/blob/main/docs/cards/template.md)
    - [Mushroom Vacuum Card](https://github.com/piitaya/lovelace-mushroom/blob/main/docs/cards/vacuum.md)
    - [Vertical Stack-In Card](https://github.com/ofekashery/vertical-stack-in-card)
    - [Vacuum Card](https://github.com/denysdovhan/vacuum-card)
    - [Xiaomi Vacuum Map Card](https://github.com/PiotrMachowski/lovelace-xiaomi-vacuum-map-card)

2. Add the [Roborock integration](https://www.home-assistant.io/integrations/roborock/) 
    Ensure your robot vacuum is integrated with Home Assistant (e.g., via Xiaomi, Roborock, or other supported platforms). Your vacuum entity ID should be something like `vacuum.my_robot`. 

4. Add the content of the [Robot Vacuum Card](card_robot_vacuum.yaml) to your dashboard.

5. Add the content of the [Robot Vacuum Conditional Card](card_robot_vacuum_conditional) to your dashboard. 

