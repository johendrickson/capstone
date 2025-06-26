# Capstone Proposal

## Overview

### Author

Jamie Hendrickson

### Project Name

Plant Pal

### Individual/Group

Individual

### Learning Goals

- New tech
  - TypeScript
  - ReactRouter
  - SMTP
  - cronjobs
  - AI integration
- DB knowledge
  - practice schemas
- process
  - deployment

### Project Description

Filling one's home is as easy as bringing home some pots and some plants. Or, that's what you think, at first. Then, suddenly you find yourself four weeks in with only a 50% survival rate of your new plants. Upkeep can be tricky, especially with a busy schedule! Plant Pal is an application designed to help plant owners manage their indoor and outdoor plants effectively.

### Project Type

Web app

## Technologies

### Main Front-end

- React
- TypeScript

### Additional Front-end

- d3.js (Not MVP)
- ReactRouter

### Main Back-end

- Python/Flask

### Additional Back-end

- SMTP
- Weather API
- scheduling library(?)

### Other

- cronjobs

### Database

- PostgreSQL
- TODO (ORM – Sequelize?)

### Deployment

- Frontend: Render
- Backend: Render
- Database: Vercel

## Wireframes

[TODO: Wireframes link](https://www.google.com)

## Feature Set

### MVP

- Plant Inventory Tracker –
Users can manage (CRUD) plants with details like name, species, watering frequency, location (inside/outside), and notes.
  - See My Plants: view of all plants
  - once plant name entered, automatic entry by AI of some data points: Scientific name, preferred Soil Conditions, edible or not, etc.

- Weather-Aware Alerts –
Users will be notified by e-mail on the morning of a day with forecasted frost, cold snap, heat wave, or dry heat spell, prompting protective action (e.g., watering or bringing plants inside).
  - heat wave identified as a temperature differential from the prior day's forecast of ≥ 15&deg;F  and over 85&deg;F
  - cold snaps are defined as temperature differential from the prior day's forecast ≥ of 10&deg; and ≤ 32&deg;F
  - frost warning is when temperature is forecasted to be ≤ 32&deg;F
  - dry heat spell is when there's forecasted no rain for ≥ 3 days and high temperatures are an average of ≥ 80&deg;F
  - e-mails sent via SMTP, using dedicated project Gmail address

- Watering Reminders –
Based on the plant’s custom watering schedule, users receive reminders to water specific plants.
  - Every N days (user's choice), the user will receive an e-mail notification for when to water
  - If multiple plants need watered on the same day, they will all be sent in a single "digest" e-mail
  - User can change how often they want any plant watered (by days)

## Schema

### `users` table

|column|type|null|id|note|
|--|--|--|--|--|
|`id`|`int`|n|PK|
|`name`|`text`|n||
|`email`|`text`/`email`(?)|n||

### `plants` table

|column|type|null|id|note|
|--|--|--|--|--|
|`id`|`int`|n|PK||
|`common_name`|`text`|n|||
|`scientific_name`|`text`|n|||
|`species`|`text`|y|||
|`preferred_soil_conditions`|`text`|y||AI-autofilled|
|`propogation_methods`|`text`|y|||
|`edible_parts`|`text`|y|||

### `user_plants` table

|column|type|null|id|note|
|--|--|--|--|--|
|`id`|`int`|n|PK||
|`user_id`|`int`|n|FK||
|`plant_id`|`int`|n|FK||
|`is_outside`|`boolean`|n|||
|`planted_date`|`datetime`|y|||

### `watering_schedules` table

|column|type|null|id|note|
|--|--|--|--|--|
|`id`|`int`|n|PK||
|`user_plant_id`|`int`|n|FK||
|`frequency_in_days`|`int`|n|||

### `watering_records` table

|column|type|null|id|note|
|--|--|--|--|--|
|`id`|`int`|n|PK||
|`user_plant_id`|`int`|n|FK||
|`date`|`datetime`|n|||
