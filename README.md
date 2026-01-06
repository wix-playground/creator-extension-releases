# אגרות הסכסוך (Conflict Letters)

A Hebrew letters/blog platform with AI-powered features for text-to-speech, PDF extraction, and an AI chat assistant.

## Features

- 📚 **Letters Library**: Browse and read published letters
- ✍️ **Admin Panel**: Create, edit, and manage letters
- 📄 **PDF Upload**: Extract text content from PDF files automatically
- 🎧 **Text-to-Speech**: Listen to letters using OpenAI's TTS with streaming
- 💬 **AI Chat Assistant**: Ask questions about the letters
- 📱 **Responsive Design**: Works on desktop and mobile
- 🔗 **Share**: Share letters via WhatsApp or copy link

## Tech Stack

### Frontend
- React 18 + TypeScript
- Vite
- TailwindCSS + shadcn/ui
- React Query (TanStack Query)
- Framer Motion

### Backend
- Express.js + TypeScript
- SQLite with Drizzle ORM
- OpenAI API (GPT-4o-mini, TTS)

## Getting Started

### Prerequisites

- Node.js 18+ 
- npm or yarn
- OpenAI API key

### Installation

1. Clone the repository:
```bash
git clone <your-repo-url>
cd conflict-letters
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file in the root directory:
```env
OPENAI_API_KEY=sk-your-openai-api-key-here
PORT=3001
DATABASE_PATH=./server/data/letters.db
UPLOAD_DIR=./server/uploads
NODE_ENV=development
```

4. Initialize the database:
```bash
npm run db:push
```

5. Start the development server:
```bash
npm run dev
```

This will start both the frontend (Vite) and backend (Express) servers concurrently.

- Frontend: http://localhost:5173
- Backend: http://localhost:3001

## Building for Production

```bash
npm run build
```

This builds both the frontend and backend.

## Deployment

### Railway

1. Connect your GitHub repository to Railway
2. Add environment variables in Railway dashboard:
   - `OPENAI_API_KEY`
   - `NODE_ENV=production`
3. Railway will automatically detect the configuration and deploy

### Docker

```bash
docker build -t conflict-letters .
docker run -p 3001:3001 -e OPENAI_API_KEY=sk-xxx conflict-letters
```

## API Endpoints

### Letters
- `GET /api/letters` - List all letters
- `GET /api/letters/:id` - Get a single letter
- `POST /api/letters` - Create a new letter
- `PUT /api/letters/:id` - Update a letter
- `DELETE /api/letters/:id` - Delete a letter

### File Upload
- `POST /api/upload` - Upload a file
- `POST /api/upload/extract` - Upload PDF and extract content

### Text-to-Speech
- `POST /api/tts/stream` - Stream TTS audio
- `POST /api/tts/generate` - Generate TTS and return base64 audio

### Chat
- `POST /api/chat/conversations` - Create a new conversation
- `GET /api/chat/conversations/:id` - Get conversation with messages
- `POST /api/chat/conversations/:id/messages` - Add a message to conversation

### LLM
- `POST /api/llm/invoke` - Invoke LLM with a prompt

## Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `OPENAI_API_KEY` | OpenAI API key for TTS and LLM | Required |
| `PORT` | Server port | `3001` |
| `DATABASE_PATH` | SQLite database file path | `./server/data/letters.db` |
| `UPLOAD_DIR` | Directory for uploaded files | `./server/uploads` |
| `NODE_ENV` | Environment mode | `development` |

## Admin Access

Default admin password: `איגרות2025`

You can change this in `src/pages/AdminLetters.tsx`.

## License

MIT
# creator-extension-releases
