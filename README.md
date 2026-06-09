[README.md](https://github.com/user-attachments/files/28758883/README.md)
# FSAFind

A web app that compares prices on FSA & HSA eligible products across major US retailers.

## Setup

### 1. Install dependencies
```bash
npm install
```

### 2. Add your Anthropic API key
```bash
cp .env.example .env
# Edit .env and add your key from https://console.anthropic.com
```

### 3. Run locally
```bash
npm run dev     # with auto-reload (Node 18+)
# or
npm start
```

Open http://localhost:3000

---

## Deploy

### Vercel (recommended — free tier)
1. Push this folder to a GitHub repo
2. Import the repo at vercel.com
3. Add `ANTHROPIC_API_KEY` in Project → Settings → Environment Variables
4. Deploy

### Railway
1. Push to GitHub, connect at railway.app
2. Add `ANTHROPIC_API_KEY` as an environment variable
3. Deploy (Railway auto-detects Node and runs `npm start`)

### Render
1. New Web Service → connect repo
2. Build command: `npm install`
3. Start command: `npm start`
4. Add `ANTHROPIC_API_KEY` in environment variables

---

## How it works

- The **frontend** (`public/index.html`) is a plain HTML/CSS/JS page served statically.
- When a user searches, it POSTs to `/api/search` on the **Express backend**.
- The backend holds the `ANTHROPIC_API_KEY` securely and calls the Anthropic API.
- Results are returned as JSON and rendered in the browser.

The API key never touches the browser — it only lives on the server.

## Project structure

```
fsafind/
├── server.js          ← Express server + API proxy
├── public/
│   └── index.html     ← Frontend (HTML/CSS/JS)
├── package.json
├── .env.example
└── README.md
```
