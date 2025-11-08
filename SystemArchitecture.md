# System Architecture - SelfOS

### Overview
SelfOS is a reflective growth system that helps users manage their evolution through structured self-awareness.  
The system is composed of three primary layers - **Frontend**, **Backend**, and **Database** with room for future **AI integration**.

---

## System Components

### 1. Frontend (Client Layer)
**Framework:** React (TypeScript)  
**Purpose:** Serve as the user interface for creating, tracking, and reflecting on growth goals.  

**Core Modules:**
- **Onboarding:** User sets up profile and defines “Version 1.0.”  
- **Backlog:** Users add and categorize personal goals (Mind / Emotion / Action).  
- **Sprint Focus:** Users select weekly focus areas with reminders and journaling prompts.  
- **Reflection / Retrospective:** Capture weekly reflections and generate summaries.  
- **Dashboard:** Visualize changelogs, growth versions, and emotional trends.

---

### 2. Backend (Application Layer)
**Framework:** Node.js + Express  
**Responsibilities:**
- Manage user authentication (JWT-based).  
- Handle CRUD operations for reflections, goals, and changelogs.  
- Perform sentiment analysis (optional AI layer).  
- Serve API endpoints to the frontend.

**Sample Endpoints:**

POST /api/auth/signup

POST /api/reflection

GET  /api/version-history

PUT  /api/goal/:id

DELETE /api/goal/:id

---

### 3. Database (Storage Layer)
**Database:** MongoDB  
**Collections:**
- `users`
- `goals`
- `reflections`
- `versions`
- `changelogs`

**Why MongoDB?**  
Its document-based structure supports flexible, human-centric data like reflections, emotions, and narratives.

---

## Communicationtion Flow
1. The **Frontend** interacts with the **Backend** via RESTful APIs.  
2. The **Backend** communicates with **MongoDB** using Mongoose ORM.  
3. (Futanalysis **AI Engine** connects via external APIs for sentiment and summary analysis.

**Simple Flow Diagram:**
User → Frontend (React) → Backend (Express API) → Database (MongoDB) ↳ (Optional AI Layer)

---

## AI Integration (Future Layer)
- **Sentiment Analysis:** Detect tone and emotion in reflections.  
- **AI Summaries:** Generate weekly growth summaries (e.g., “Improved self-trust this week”).  
- **Possible Tools:** OpenAI GPT, Hugging Face Transformers.  

---

## Infrastructure
| Component | Service |
|------------|----------|
| Frontend Hosting | Vercel |
| Backend Hosting | Render / Heroku |
| Database | MongoDB Atlas |
| CI/CD | GitHub Actions |
| Version Control | Git + GitHub |

---

## Security
- End-to-end encryption for reflection entries (AES-256).  
- Secure JWT authentication.  
- Regular database backups and anonymized analytics.

---

## Scalability
- Modular codebase ready for mobile extension.  
- Cloud-based database allows multi-platform scaling.  
- Microservice-ready backend structure.

---

## Summary
SelfOS merges the logic of product iteration with the empathy of human reflection.  
Each user interaction; from writing a reflection to viewing their “growth changelog”, flows through a calm, minimal, and secure ecosystem built for one goal:

> Helping people **see themselves evolving**: One version at a time.
> 
