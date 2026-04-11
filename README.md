# Drift

Drift is an outdoor discovery and planning app built to help people stop scrolling and start going.

Instead of digging through blogs, maps, weather apps, and park sites, Drift helps users:

- discover curated outdoor experiences
- filter by travel time, vibe, effort, and family fit
- save picks into collections
- compare options side by side
- turn a good idea into an actual trip plan

## What Drift Feels Like

Drift is designed to feel less like a directory and more like a smart outdoor guide.

| Discover | Plan | Decide |
| --- | --- | --- |
| Swipe through curated experiences | Save picks into collections | Compare tradeoffs and generate a trip plan |
| See why a pick fits you | Organize by board or mood | Use live weather and timing context |
| Get weather-aware suggestions | Build shortlists fast | Go outside faster |

## Core Experience

### 1. Onboarding
Users pick a home base, travel range, and activity preferences so the experience starts personalized.

### 2. Discover
The main screen is a swipeable outdoor deck with:

- personalized recommendations
- live weather context
- local-first filtering
- keyboard-friendly desktop controls
- Drifty, the mascot guide

### 3. Detail View
Each experience has a richer editorial view with:

- why this fits
- why now
- maps link
- share support
- save-to-collection flow

### 4. Collections
Saved experiences become a real planning workspace with:

- custom collections
- featured picks
- compare mode
- trip-planning modal
- board-level sorting and filtering

## Why We Built It

Nature is meant to be explored, but choosing what to do is often harder than the adventure itself.

We built Drift to reduce that friction and make outdoor planning feel:

- faster
- more personal
- more timely
- more fun

## Tech Stack

### Frontend

- React
- Vite
- JavaScript

### Backend

- FastAPI
- Python
- Supabase Auth

### APIs and Services

- Anthropic API
- Open-Meteo API
- Supabase

### Data

- Seeded outdoor experience dataset for demo reliability
- Local persisted user state

## Project Structure

```text
.
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── data/
│   │   ├── lib/
│   │   └── theme/
├── backend/
│   └── app/
├── docx/
└── AGENT.md
```

## Local Setup

### 1. Frontend

```bash
cd frontend
npm install
npm run dev
```

Frontend runs on:

```text
http://localhost:5173
```

### 2. Backend

```bash
cd backend
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --reload
```

Backend runs on:

```text
http://localhost:8000
```

## Environment Variables

### Frontend

Create `frontend/.env.local`

```env
VITE_SUPABASE_URL=...
VITE_SUPABASE_ANON_KEY=...
# Optional
VITE_API_BASE=http://localhost:8000
```

### Backend

Create `backend/.env`

```env
ANTHROPIC_API_KEY=...
RIDB_API_KEY=...
SUPABASE_URL=...
SUPABASE_SERVICE_ROLE_KEY=...
RATE_LIMIT_MAX_REQUESTS=5
RATE_LIMIT_WINDOW_SECONDS=60
```

See:

- `frontend/.env.example`
- `backend/.env.example`

## Current Highlights

- desktop-first discovery flow
- Drifty mascot integrated into the experience
- compare mode for collections
- local fallback trip planning when live AI planning fails
- per-user onboarding persistence
- live weather for supported seeded locations
- seeded data fallback so demos stay reliable

## Demo Flow

If you want the fastest repo walkthrough, use this order:

1. Open the welcome screen
2. Sign in with Google
3. Complete onboarding
4. Swipe through Discover
5. Open an experience detail page
6. Save it into a collection
7. Open Collections
8. Compare picks
9. Generate a trip plan

## Notes

- The frontend is intentionally optimized for a polished desktop demo.
- The app supports live weather, but also falls back gracefully when outside services fail.
- The seeded experience catalog exists so the product still feels full and stable during demos.

## Team

Built by:

- Shaan Kal
- Viswas Vallabeneni
- Raghav Senthilkumar

## Status

Drift placed 3rd at the Cursor Hackathon at UW-Madison, and we are continuing development.
