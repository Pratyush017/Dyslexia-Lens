## Dyslexia Lens

**Dyslexia Lens** is a free, AI-driven reading assistant built to support students with dyslexia. The platform enables users to upload PDFs and receive simplified, accessible text using phonetic segmentation, structured formatting, and visual learning cues to improve comprehension.

---

## Core Features

* **Bring Your Own API Key** – Integrate your own Google Gemini API key (free tier supported).
* **PDF Upload & Processing** – Upload documents and receive AI-powered simplification.
* **Phonetic Chunking** – Breaks complex words into readable syllables (e.g., *Un·der·stand·ing*).
* **Intelligent Simplification** – Rewrites content at approximately a 5th-grade reading level.
* **Visual Anchors** – Adds contextual emojis and short definitions to reinforce understanding.
* **Text-to-Speech** – Converts simplified text into speech for auditory learning.
* **Progress Monitoring** – Tracks words read, XP points, and user level progression.
* **Secure Authentication** – Firebase authentication combined with JWT-based authorization.
* **Accessible UI Design** – Clean, distraction-reduced interface with focus mode and reading ruler.

---

## Technology Stack

### Frontend

* React – Component-based UI framework
* Vite – Fast build tooling
* Axios – HTTP client
* React Router – Client-side navigation
* Firebase Authentication – Secure login (Google sign-in supported)

### Backend

* Node.js + Express – RESTful API server
* Prisma – ORM for database interaction
* PostgreSQL – Relational database
* JWT – Token-based authentication
* Multer – File upload middleware

### AI Engine

* Python + FastAPI – AI microservice
* Google Gemini 2.5 Flash – Text simplification and analysis
* Pillow (PIL) – Image processing

---

## System Requirements

Ensure the following are installed:

* Node.js (v16+)
* Python (v3.8+)
* PostgreSQL (v12+)
* Git

---

## Setup Instructions

### 1. Clone Repository

```bash
git clone https://github.com/abhijeet586/dyslexia-lens.git
cd dyslexia-lens
```

### 2. Configure Database

```bash
createdb dyslexia_db
```

---

### 3. Backend Configuration

```bash
cd server
npm install
```

Create a `.env` file:

```
DATABASE_URL="postgresql://USER:PASSWORD@localhost:5432/dyslexia_db?schema=public"
JWT_SECRET="your_secret_key"
PORT=5000
```

Run Prisma migrations and start server:

```bash
npx prisma migrate dev
npm start
```

---

### 4. Frontend Setup

```bash
cd client
npm install
npm run dev
```

---

### 5. AI Engine Setup

```bash
cd ai-engine
python -m venv venv
```

Activate virtual environment:

* Windows:

```bash
venv\Scripts\activate
```

* macOS/Linux:

```bash
source venv/bin/activate
```

Install dependencies and launch AI service:

```bash
pip install -r requirements.txt
python -m uvicorn app.main:app --reload --port 8000
```

---

### 6. Generate Gemini API Key

1. Visit Google AI Studio
2. Sign in with your Google account
3. Create a new API key
4. Copy and save the key

---

## Running the Application

Ensure all services are active:

* Frontend → [http://localhost:5173](http://localhost:5173)
* Backend → [http://localhost:5000](http://localhost:5000)
* AI Engine → [http://localhost:8000](http://localhost:8000)

Then:

1. Open [http://localhost:5173](http://localhost:5173)
2. Sign up or log in
3. Add your Gemini API key in the Dashboard
4. Upload a PDF
5. Begin reading with AI assistance
6. Monitor reading progress and XP growth

---

## Project Structure

```
dyslexia-lens/
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── pages/          # Application pages
│   │   ├── context/        # State management
│   │   └── hooks/          # Custom hooks
│   └── package.json
├── server/                 # Node.js backend
│   ├── src/
│   │   ├── controllers/    # Business logic
│   │   ├── routes/         # API endpoints
│   │   ├── middlewares/    # Auth & upload middleware
│   │   └── config/         # Firebase config
│   ├── prisma/             # Database schema
│   └── package.json
├── ai-engine/              # Python AI microservice
│   ├── app/
│   │   ├── main.py         # FastAPI entry point
│   │   └── ai_service.py   # Gemini integration
│   └── requirements.txt
└── README.md
```

---

## How It Works

* **Register / Log In** – Authenticate via email or Google
* **Add API Key** – Save your Gemini API key
* **Upload Document** – Submit a PDF for analysis
* **AI Processing** – Text is simplified and formatted
* **Read & Listen** – Engage with accessible text and TTS
* **Track Growth** – Monitor performance metrics and learning level

---

## Security Considerations

* API keys are stored locally in browser storage
* `.env` files must not be committed
* Sensitive credentials should always use environment variables
* Firebase manages secure authentication

---

## Limitations

* Requires internet access for AI processing
* Gemini free tier has rate limits
* Large PDFs may increase processing time
* Currently optimized for English-language documents

---

## Contribution

Pull requests and improvements are welcome.

---

## License

Distributed under the MIT License.

---

## Authors

**Pratyush Raj**
LinkedIn: [https://www.linkedin.com/in/pratyushraj0176/](https://www.linkedin.com/in/pratyushraj0176/)

**Aron Chandel** 
Github: [https://github.com/aronchandel]
**Abhijeet Senapati** 
Github: [https://github.com/abhijeet586]

---

## Acknowledgments

* Google Gemini AI for natural language processing
* Firebase for authentication infrastructure
* Open-source contributors and libraries used throughout the project

---

*This project is intended for educational use and is not currently deployed. Follow the setup instructions above to run it locally.*
