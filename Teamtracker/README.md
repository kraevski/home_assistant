# Team tracker card for Home Assistant

![teamtracker](https://github.com/user-attachments/assets/d1fee795-46aa-4881-a63f-97e8e99303dd)

Automatic cards that are created and display the next game for your faviourite teams.

## Installation guide:

1. Install the following third-party tools using [HACS](https://www.hacs.xyz/):
    - [Auto-entities](https://github.com/thomasloven/lovelace-auto-entities)
    - [Card Mod](https://github.com/thomasloven/lovelace-card-mod)
    - [Layout Card](https://github.com/thomasloven/lovelace-layout-card)
    - [Teamtracker Card](https://github.com/vasqued2/ha-teamtracker-card)

2. Add the [Team Tracker integration](https://github.com/vasqued2/ha-teamtracker) and configure it to track your favourite sport teams/players.
This will create sensors with the name that you've put in `Friendly name` in each configuration.

3. Add the content of the [Teamtracker Card](card_team_tracker.yaml) to your dashboard.

4. I've added the configurations only for my favourite teams and this is why I am using `integration_entities("teamtracker")`. 
The visibility condition is to display a card only if the sensor status is `PRE` and the start date and time of the game is less than 3 days (timestamp difference `259200`). 
The order of the cards is by `date`, meaning the earliest upcoming event is shown first.

