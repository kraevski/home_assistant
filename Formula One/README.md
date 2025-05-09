# Formula One card for Home Assistant

<img src="https://github.com/user-attachments/assets/30868916-d700-4ae7-ad5f-1f9b7e223615" width="600">
<img src="https://github.com/user-attachments/assets/9df41446-88ac-498f-a545-ecfe01dd1ab1" width="200">

A card showing the next race with countdown until the next raceweek event (practice, qualifying, sprint, race). 

The card is clickable and opens a pop-up with detailed information about the next race, the standings and the schedule for the next 5 races.

## Installation guide:

1. Install the following third-party tools using [HACS](https://www.hacs.xyz/):
    - [Browser Mod](https://github.com/thomasloven/hass-browser_mod)
    - [Button Card](https://github.com/custom-cards/button-card)
    - [Card Mod](https://github.com/thomasloven/lovelace-card-mod)
    - [Formula One Card](https://github.com/marcokreeft87/formulaone-card)
    - [Layout Card](https://github.com/thomasloven/lovelace-layout-card)
    - [Vertical Stack-In Card](https://github.com/ofekashery/vertical-stack-in-card)

2. Add the [Team Tracker integration](https://github.com/vasqued2/ha-teamtracker) and configure it to track the Formula One League for all Teams (with regex `*`).
This will create a sensor with the name that you've put in `Friendly name`.

<img src="https://github.com/user-attachments/assets/934edd8d-e7da-43fa-98d7-24b3476a5da0" width="400">

4. Add the content of the [Formula One Card](card_formula_one.yaml) to your dashboard.

5. To have the weather conditions for the next race you can get an API key [here](https://www.visualcrossing.com/sign-up/) or use the [F1 sensor integration](https://github.com/Nicxe/f1_sensor).

