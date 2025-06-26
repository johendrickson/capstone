# Plant Pal

## Overview
Plant Pal is an application designed to help plant enthusiasts manage their indoor and outdoor plants effectively.

## Features

1. Plant Inventory Tracker
Users can add plants with details like name, species, watering frequency, location (inside/outside), and notes.

2. Weather-Aware Alerts
Uses a weather API to notify users when a frost, drought, or heat wave is coming, prompting protective action (e.g., watering or bringing plants inside).

3. Watering Reminders
Based on the plant’s watering schedule, users receive reminders to water specific plants.

## Implementation thoughts
1. Plant Inventory Tracker

- CRUD operations. relatively simple.
- auto-fill form based on first inputs? e.g. if user inputs scientific name, auto-fill the common name; auto-suggest scientific names based on first few characters; etc.
- use AI to generate soil conditions for the plant species based on whether it is inside or outside
- Plant input form:
  - Common name(s)
  - Scientific name
  - Species
  - Inside or outside?
  - Soil conditions (AI autofilled)
  - Planted date:
  - Propogation methods
  - Vegetable?
  - Edible parts

2. Weather-Aware Alerts

- collect a user's zip code or lat/lon coordinates to fetch weather data
- weather API will have temperature, wind, humidity, info on presence of thunderstorms, blizzards, etc.
- weather API *might* have categorization of whether weather is inclement or not. categorizing as "inclement" might have to be part of my code.
- e-mail notifications. can use SMTP library.

3. Watering Reminders

- e-mail notifications. can use SMTP library.
- user sets frequency of reminders: weeks, days, hours, minutes, etc. but, as they set the reminder, plant-specific watering info appears as helpful hints.
- TODO: see if AI can be used to generate soil condition info, as that will help give the user an idea of a good watering frequency.


## Decisions
- DB: what ORM?
- schema: just `plants` w/ `user_id` column? or join table: `users_plants`?
- data usage: store soil condition preferences in table, or use AI every time to generate?
