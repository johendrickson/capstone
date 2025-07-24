# Plant Pal

## Author
**Jamie Hendrickson**

## Project Name
**Plant Pal**

## Individual/Group
**Individual**

---

## Learning Goals

### New Tech
- TypeScript  
- ReactRouter  
- SMTP  
- Cronjobs  
- AI integration  

### DB Knowledge
- Practice schemas  

### Process
- Deployment  

---

## Project Description

Filling one's home is as easy as bringing home some pots and some plants. Or, that's what you think, at first. Then, suddenly you find yourself four weeks in with only a 50% survival rate of your new plants. Upkeep can be tricky, especially with a busy schedule!  
**Plant Pal** is an application designed to help plant owners manage their indoor and outdoor plants effectively.

---

## Project Type
**Web App**

---

## Technologies

### Main Front-end
- React  
- TypeScript  

### Additional Front-end
- d3.js *(Not MVP)*  
- ReactRouter  

### Main Back-end
- Python / Flask  

### Additional Back-end
- SMTP  
- Weather API  
- Scheduling library (?)  

### Other
- Cronjobs  

### Database
- PostgreSQL  
- TODO: ORM – Sequelize?  

---

## Deployment
- **Frontend:** Render  
- **Backend:** Render  
- **Database:** Vercel  

---

## Wireframes
[Wireframes Link](https://drive.google.com/file/d/1iO4pV2vMbS6Teh7Acsd-Sk8-RPpR5ngF/view?usp=sharing)

---

## Feature Set

### MVP

#### 🌱 Plant Inventory Tracker
Users can manage (CRUD) plants with details like:
- Name
- Species
- Watering frequency
- Location (inside/outside)
- Notes  

Features:
- **See My Plants:** view all plants  
- After entering a plant name, AI auto-fills:
  - Scientific name  
  - Preferred soil conditions  
  - Edible or not  
  - Etc.

#### 🌦️ Weather-Aware Alerts
Users receive e-mail alerts on the morning of a:
- **Frost warning:** Forecast ≤ 32°F  
- **Cold snap:** ≥10° drop & ≤ 32°F  
- **Heat wave:** ≥15°F increase & over 85°F  
- **Dry heat spell:** ≥3 days no rain + avg. ≥ 80°F  

> Emails are sent via SMTP using a dedicated project Gmail account.

#### 💧 Watering Reminders
- Based on each plant’s custom watering schedule.
- Email reminders sent **every N days** (user-defined).
- Multiple reminders in one digest email if needed.
- Users can update frequency anytime.

---

## Schema

### `users` Table

| Column | Type       | Null | ID | Note |
|--------|------------|------|----|------|
| id     | int        | n    | PK |      |
| name   | text       | n    |    |      |
| email  | text/email | n    |    |      |

### `plants` Table

| Column                | Type | Null | ID | Note           |
|-----------------------|------|------|----|----------------|
| id                    | int  | n    | PK |                |
| common_name           | text | n    |    |                |
| scientific_name       | text | n    |    |                |
| species               | text | y    |    |                |
| preferred_soil_conditions | text | y |    | AI-autofilled  |
| propogation_methods   | text | y    |    |                |
| edible_parts          | text | y    |    |                |

### `user_plants` Table

| Column        | Type     | Null | ID | Note |
|---------------|----------|------|----|------|
| id            | int      | n    | PK |      |
| user_id       | int      | n    | FK |      |
| plant_id      | int      | n    | FK |      |
| is_outside    | boolean  | n    |    |      |
| planted_date  | datetime | y    |    |      |

### `watering_schedules` Table

| Column           | Type | Null | ID | Note |
|------------------|------|------|----|------|
| id               | int  | n    | PK |      |
| user_plant_id    | int  | n    | FK |      |
| frequency_in_days| int  | n    |    |      |

### `watering_records` Table

| Column        | Type     | Null | ID | Note |
|---------------|----------|------|----|------|
| id            | int      | n    | PK |      |
| user_plant_id | int      | n    | FK |      |
| date          | datetime | n    |    |      |
