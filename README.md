# 🌱 Plant Pal

Plant Pal is a full-stack web application that helps users track and care for their plants.  
It combines AI-generated plant information, location-based weather alerts, and customizable watering reminders into one tool.

- **Frontend Repo:** [link-to-frontend-repo](https://github.com/johendrickson/capstone-frontend)
- **Backend Repo:** [link-to-backend-repo](https://github.com/johendrickson/capstone-backend)

---

## 📖 Overview

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

**Frontend**  
- React (TypeScript)  
- React Router  

**Backend**  
- Python (Flask)  
- PostgreSQL (Supabase for deployment)  
- SMTP (email notifications)  
- LocationIQ API (geocoding)  
- OpenWeather API (weather data)  
- Google Gemini AI API (AI autofill)  
- Cron jobs (scheduled alerts & reminders)
- GitHub Actions  

**Deployment**  
- Frontend: Render  
- Backend: Render  
- Database: Supabase  

---

## 📸 Screenshots / Wireframes
[View initial wireframes](https://drive.google.com/file/d/1iO4pV2vMbS6Teh7Acsd-Sk8-RPpR5ngF/view?usp=sharing)
<img width="1787" height="1089" alt="image" src="https://github.com/user-attachments/assets/ab09bd79-5556-4d22-a87d-066d3faa5b13" />


---

## Author
**Jamie Hendrickson**  
Ada Developers Academy, Cohort 23
