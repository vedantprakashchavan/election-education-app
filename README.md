# Election Process Education App

An interactive web application to help users understand the election process, timelines, voting steps, and key concepts — built for the Hack2Skill "Election Process Education" challenge.

## Features

- **Overview** — Types of elections, key facts about Indian democracy
- **Timeline** — All 7 phases from announcement to government formation
- **How to Vote** — Step-by-step voting guide with EVM explanation
- **FAQ** — Accordion-style answers to common voter questions
- **Quiz** — 8-question interactive quiz with instant scoring
- **Glossary** — Searchable definitions (ECI, EVM, VVPAT, NOTA, MCC, and more)
- **AI Assistant** — Built-in chatbot answering election questions

## Tech Stack

- Pure HTML, CSS, JavaScript — zero dependencies
- Responsive design (mobile + desktop)
- Nginx on Docker for Cloud Run deployment

---

## Deployment Guide

### 1. Clone & push to GitHub

```bash
git init
git add .
git commit -m "Initial commit - Election Process Education App"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/election-education-app.git
git push -u origin main
```

### 2. Deploy to Google Cloud Run

**Prerequisites:** Google Cloud SDK installed and authenticated.

```bash
# Set your project
gcloud config set project YOUR_PROJECT_ID

# Build and push the Docker image
gcloud builds submit --tag gcr.io/YOUR_PROJECT_ID/election-app

# Deploy to Cloud Run
gcloud run deploy election-app \
  --image gcr.io/YOUR_PROJECT_ID/election-app \
  --platform managed \
  --region asia-south1 \
  --allow-unauthenticated \
  --port 8080
```

After deployment, Cloud Run will give you a URL like:
`https://election-app-xxxxxxxx-el.a.run.app`

Use that URL as your **Deployed Link (Cloud Run URL)** in the hack2skill submission form.

---

## Local Testing

```bash
# Option 1: Open directly in browser
open index.html

# Option 2: Using Python
python3 -m http.server 8000
# Visit: http://localhost:8000

# Option 3: Using Docker
docker build -t election-app .
docker run -p 8080:8080 election-app
# Visit: http://localhost:8080
```

---

## Project Structure

```
election-app/
├── index.html      # Main application (single-file app)
├── Dockerfile      # Container config for Cloud Run
└── README.md       # This file
```

---

## Submission Checklist (Hack2Skill)

- [x] Challenge: Election Process Education
- [x] GitHub Repository: public repo with this code
- [x] Deployed Link: Cloud Run URL (https://...)
- [x] LinkedIn Post: Share your project on LinkedIn

---

*Built for Hack2Skill Virtual Prompt Challenge · Election Process Education*
