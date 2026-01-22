# Plant Pal 🌱

Plant Pal is a full-stack web application that helps users track and care for their plants.

It combines AI-generated plant information, location-based weather alerts, and customizable watering reminders into one tool.

- **Frontend Repository:** [Plant Pal Frontend – React + TypeScript interface](https://github.com/johendrickson/capstone-frontend)
- **Backend Repository:** [Plant Pal Backend – Flask API and database services](https://github.com/johendrickson/capstone-backend)

---

## Overview

Plant Pal is designed for anyone who wants an easier way to manage indoor and outdoor plants.

Users can store plant details, receive email reminders for watering, and get notified about weather conditions that might harm their plants.

Key capabilities:
- Store and manage plant information (CRUD operations)
- AI autofill for plant details based on scientific name
- Email alerts for frost, heat waves, cold snaps, and dry heat spells
- Customizable watering schedules with reminders
- Location-based features powered by ZIP code to coordinate conversion

---

## Features

- **Plant Inventory Management** – Create, view, update, and delete plant records with fields such as scientific name, common name, watering frequency, location (indoor/outdoor), and optional notes.
- **AI-Autofill** – When a scientific name is entered, the Gemini API automatically fills in optional plant details such as preferred soil type, propagation methods, edible parts, and pet safety. All AI-generated data can be reviewed and edited by the user.
- **Weather Alerts** –  The backend checks daily forecasts and sends email alerts for conditions like frost, heat waves, cold snaps, or extended dry heat spells, helping users take preventive action for outdoor plants.
- **Watering Reminders** – Based on a plant’s custom watering schedule, users receive email reminders. Multiple plants due on the same day are combined into a single digest email.
- **Zip-to-Coordinates Conversion** – At signup or when updating a ZIP code, the app uses the LocationIQ API to convert the ZIP code into latitude and longitude coordinates, which are stored and used for weather forecasting.

---

## Tech Stack

### Frontend
- React (TypeScript)
- React Router

### Backend
- Python (Flask)
- PostgreSQL (Supabase for deployment)
- SMTP (email notifications)
- LocationIQ API (geocoding)
- OpenWeather API (weather data)
- Google Gemini AI API (AI autofill)
- Cron jobs (scheduled alerts & reminders)
- GitHub Actions

### Deployment
- Frontend: Render
- Backend: Render
- Database: Supabase

---

## Local Development (Docker)

Plant Pal can be run locally using Docker Compose, which spins up the frontend and backend together with a single command.

This setup is recommended for contributors who want a consistent local environment without installing dependencies manually.

### Prerequisites
- Docker
- Docker Compose (included with Docker Desktop)

### Running the app locally

From the root of the **main (capstone) repository**, run:

```bash
docker compose up --build
```

This will:
- Build and start the Flask backend on http://localhost:5000
- Build and serve the React frontend on http://localhost:3000
- Connect services using Docker’s internal network

Once running, open your browser and navigate to:

http://localhost:3000

### Environment variables

- The backend reads configuration (such as database credentials and API keys) from environment variables. For more info on the needed credentials, see the [Plant Pal Backend repository](https://github.com/johendrickson/capstone-backend).
- For local development, these can be provided via a .env file referenced in `docker-compose.yml`.
- For deployment, environment variables are managed by the hosting platform (Render).

No code changes are required to switch between local and deployed environments.

### Stopping the containers

To stop all running services:

```bash
docker compose down
```

---

## 📸 Screenshots / Wireframes

<div align="center">

[View initial wireframes](https://drive.google.com/file/d/1iO4pV2vMbS6Teh7Acsd-Sk8-RPpR5ngF/view?usp=sharing)
[Visuals of the final product](https://drive.google.com/drive/folders/1XVHepADxldqdq65OJZPVia1a2eWTYcla?usp=drive_link)

<img width="787" height="589" alt="Plant Pal Home Page" src="https://github.com/user-attachments/assets/ab09bd79-5556-4d22-a87d-066d3faa5b13" />

<img width="717" height="544" alt="Original wireframe for Plant Pal homepage" src="https://github.com/user-attachments/assets/0b4d5b62-628a-4da4-b850-45ecd7ccb1a3" />

</div>

---

## Author
**Jamie Hendrickson**
Ada Developers Academy, Cohort 23
