# Real-Time Chat Application

A React/Mantine frontend and FastAPI backend for authenticated one-to-one messaging.

## Project Structure

- `frontend/`: React/Vite application with login, registration, contacts, friend requests, chat history, responsive layout, and WebSocket messaging.
- `backend/`: FastAPI application with JWT/bcrypt authentication, MongoDB Atlas persistence, friend-request chat creation, REST history, and `/ws/chat` real-time messaging.

## Local Development

### Backend

```bash
cd backend
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload --port 8000
```

Required backend environment variable:

```text
MONGO_URI=<MongoDB Atlas connection string>
JWT_SECRET=<long random JWT signing secret>
```

### Frontend

```bash
cd frontend
npm install
npm run dev
```

For local development, create an ignored `.env.local` file containing:

```text
VITE_CHAT_API_URL=http://127.0.0.1:8000/api
VITE_CHAT_WS_URL=ws://127.0.0.1:8000/ws/chat
```

## Deployment

- Backend: Render, root directory `backend`.
- Frontend: Netlify or Vercel, root directory `frontend`.
- MongoDB: MongoDB Atlas.

Frontend deployment variables:

```text
VITE_CHAT_API_URL=https://<render-service>.onrender.com/api
VITE_CHAT_WS_URL=wss://<render-service>.onrender.com/ws/chat
```

Never commit `.env` files, tokens, database credentials, or generated dependencies.
