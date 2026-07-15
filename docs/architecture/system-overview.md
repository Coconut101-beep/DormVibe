
# DormVibe System Overview

DormVibe is a student accommodation discovery platform designed to help university students identify housing options that match their lifestyle, personality, and community preferences.

The platform combines preference collection, recommendation logic, and personalized room analysis into a single user experience.


---

## System Flow

Landing Page

↓

User Authentication

↓

Personal Preference Quiz

↓

Recommendation Processing

↓

Room Recommendation Results

↓

Room DNA Analysis

↓

Checkout Flow

↓

Profile Dashboard

---

## Architecture Overview

### Frontend Layer

Responsible for:

- User interface rendering
- User interactions
- State management
- Routing and navigation

Technologies:

- React
- TypeScript
- Vite
- Tailwind CSS
- Zustand

---

### Backend Layer

Responsible for:

- API endpoints
- Authentication workflows
- Business logic
- Data processing

Technologies:

- Express.js
- Node.js

---

### Database Layer

Responsible for:

- User account storage
- Quiz response storage
- Recommendation persistence

Technology:

- Supabase

---

## Development Workflow

1. User completes onboarding quiz
2. Quiz data is processed
3. Recommendation results are generated
4. Room DNA analysis is created
5. User explores accommodation options
6. User proceeds through checkout flow
7. Data is stored and accessible through the profile dashboard

---

## Deployment

Frontend deployment was originally hosted on Vercel during development and demonstration stages.

This repository is maintained as a portfolio showcase of the project architecture, frontend implementation, and product design process.

