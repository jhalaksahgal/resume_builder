# Resume Builder

A full-stack resume builder application that helps users create, manage, enhance, and preview professional resumes.

## Features

- User registration and login
- Resume creation, editing, and deletion
- Resume preview and public sharing
- AI-powered resume assistance
  - Enhance professional summaries
  - Improve job descriptions
  - Upload and parse resumes
- Secure protected routes with token-based authentication
- Image upload support for resume content

## Tech Stack

### Frontend
- React 19
- Vite
- React Router DOM
- Redux Toolkit
- Axios
- Tailwind CSS
- React Hot Toast
- Lucide React
- React PDF Text

### Backend
- Node.js
- Express
- MongoDB with Mongoose
- JWT authentication
- Multer for uploads
- CORS
- OpenAI integration
- ImageKit SDK

## Project Structure

```text
resume_builder/
├── client/        # React frontend
└── server/        # Express API
```

## Getting Started

### Prerequisites
- Node.js and npm
- MongoDB database
- OpenAI API key
- ImageKit credentials

### Installation

Clone the repository and install dependencies for both apps:

```bash
git clone https://github.com/jhalaksahgal/resume_builder.git
cd resume_builder
npm install
cd client && npm install
cd ../server && npm install
```

### Environment Variables

Create a `.env` file inside `server/` with the required variables. Based on the codebase, you will likely need values similar to:

```env
PORT=3000
FRONTEND_URL=http://localhost:5173
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
OPENAI_API_KEY=your_openai_api_key
IMAGEKIT_PUBLIC_KEY=your_imagekit_public_key
IMAGEKIT_PRIVATE_KEY=your_imagekit_private_key
IMAGEKIT_URL_ENDPOINT=your_imagekit_url_endpoint
```

If the frontend uses an API base URL config, set that as well in the client environment configuration.

## Running the App

### Start the backend

```bash
cd server
npm run start
```

For development with auto-restart:

```bash
npm run server
```

### Start the frontend

```bash
cd client
npm run dev
```

## Available API Routes

### Users
- `POST /api/users/register` — Register a new user
- `POST /api/users/login` — Log in a user
- `GET /api/users/data` — Get authenticated user data
- `GET /api/users/resumes` — Get resumes for the authenticated user

### Resumes
- `POST /api/resumes/create` — Create a new resume
- `PUT /api/resumes/update` — Update an existing resume
- `DELETE /api/resumes/delete/:resumeId` — Delete a resume
- `GET /api/resumes/get/:resumeId` — Get a private resume by ID
- `GET /api/resumes/public/:resumeId` — Get a public resume by ID

### AI Tools
- `POST /api/ai/enhanced-pro-sum` — Enhance a professional summary
- `POST /api/ai/enhanced-job-desc` — Enhance a job description
- `POST /api/ai/upload-resume` — Upload and process a resume

## Frontend Pages

- `/` — Landing page
- `/app` — Dashboard layout
- `/app/builder/:resumeId` — Resume builder/editor
- `/view/:resumeId` — Public resume preview

## Notes

- Protected endpoints require an authorization token in the request headers.
- The backend connects to MongoDB on startup.
- The frontend fetches authenticated user data on load using the stored token.
