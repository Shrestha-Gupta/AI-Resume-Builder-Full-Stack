# AI Resume Builder

An AI-powered, full-stack resume builder that helps users create professional, customizable, and ATS-friendly resumes with ease. Users can build resumes from scratch, import existing resumes, enhance their content using AI, customize templates, and download or share their resumes.

## Live Demo

- **Frontend:** https://ai-resume-builder-full-stack-mu.vercel.app
- **Backend API:** https://ai-resume-builder-full-stack-1.onrender.com
- **GitHub Repository:** https://github.com/Shrestha-Gupta/AI-Resume-Builder-Full-Stack

## Features

- **User Authentication:** Secure user registration and login using JWT-based authentication.
- **Resume Creation:** Create and manage multiple resumes with a user-friendly editor.
- **Customizable Templates:** Choose different resume templates and personalize accent colors.
- **AI-Powered Content Enhancement:** Improve professional summaries and job descriptions using AI.
- **Resume Import:** Upload an existing resume in PDF format and extract its information using AI.
- **Profile Management:** Add and update personal information, education, professional experience, projects, and skills.
- **Profile Image Upload:** Upload profile images with ImageKit integration.
- **Live Resume Preview:** See changes reflected in the resume preview.
- **Public Resume Sharing:** Generate shareable links for publicly accessible resumes.
- **PDF Download:** Download the completed resume as a PDF.
- **Dashboard:** Manage, access, and organize created resumes.

## Tech Stack

### Frontend
- React.js 19
- Vite
- JavaScript
- React Router DOM
- Redux Toolkit
- Tailwind CSS 4
- Axios
- Lucide React
- React Hot Toast

### Backend
- Node.js
- Express.js 5
- MongoDB
- Mongoose
- JSON Web Tokens (JWT)
- Bcrypt
- Multer

### Third-Party Integrations
- **Google Gemini API:** AI-powered resume content enhancement and resume data extraction through an OpenAI-compatible API interface.
- **ImageKit:** Profile image upload and image processing.
- **MongoDB Atlas:** Cloud database hosting.

### Deployment
- Vercel – Frontend hosting
- Render – Backend hosting
- MongoDB Atlas – Database hosting

## Project Structure

```text
AI-Resume-Builder-Full-Stack/
│
├── client/
│   ├── public/
│   ├── src/
│   │   ├── app/
│   │   ├── components/
│   │   ├── configs/
│   │   ├── pages/
│   │   └── ...
│   ├── .env.example
│   ├── package.json
│   └── vite.config.js
│
├── server/
│   ├── configs/
│   ├── controllers/
│   ├── middlewares/
│   ├── models/
│   ├── routes/
│   ├── .env.example
│   ├── package.json
│   └── server.js
│
├── .gitignore
└── README.md
```

## Getting Started

Follow these instructions to run the project locally.

### 1. Clone the Repository

```bash
git clone https://github.com/Shrestha-Gupta/AI-Resume-Builder-Full-Stack.git
```

```bash
cd AI-Resume-Builder-Full-Stack
```

### 2. Install Frontend Dependencies

```bash
cd client
npm install
```

### 3. Install Backend Dependencies

Open another terminal from the project root:

```bash
cd server
npm install
```

### 4. Configure Environment Variables

Create a `.env` file inside the `server` directory.

Add the following variables:

```env
JWT_SECRET=your_jwt_secret
MONGODB_URI=your_mongodb_connection_string
IMAGEKIT_PRIVATE_KEY=your_imagekit_private_key
OPENAI_API_KEY=your_google_gemini_api_key
OPENAI_BASE_URL=https://generativelanguage.googleapis.com/v1beta/openai/
OPENAI_MODEL=gemini-2.5-flash
```

Create a `.env` file inside the `client` directory:

```env
VITE_BASE_URL=http://localhost:3000
```

**Note:** Replace the placeholder values with your own credentials. Never commit `.env` files or expose API keys in the frontend.

### 5. Run the Backend

From the `server` directory:

```bash
npm start
```

The backend will run at:

```text
http://localhost:3000
```

### 6. Run the Frontend

From the `client` directory:

```bash
npm run dev
```

Open the application at:

```text
http://localhost:5173
```

## API Endpoints

The backend exposes the following REST API endpoints.

### Authentication & User APIs

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/users/register` | Register a new user |
| POST | `/api/users/login` | Authenticate a user |
| GET | `/api/users/data` | Retrieve authenticated user data |
| GET | `/api/users/resumes` | Retrieve user's resumes |

### Resume APIs

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/resumes/create` | Create a new resume |
| PUT | `/api/resumes/update` | Update resume information |
| DELETE | `/api/resumes/delete/:resumeId` | Delete a resume |
| GET | `/api/resumes/get/:resumeId` | Retrieve a resume |
| GET | `/api/resumes/public/:resumeId` | Retrieve a public resume |

### AI APIs

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/ai/enhance-pro-sum` | Enhance professional summary |
| POST | `/api/ai/enhance-job-desc` | Enhance job descriptions |
| POST | `/api/ai/upload-resume` | Extract resume information using AI |

Protected endpoints require JWT authentication.

## Deployment Architecture

The application uses a separate frontend and backend deployment architecture.

```text
                  Users
                    |
                    v
             Vercel Frontend
              React + Vite
                    |
              Axios API Calls
                    |
                    v
             Render Backend
              Node + Express
                    |
          +---------+----------+
          |         |          |
          v         v          v
       MongoDB   Gemini API   ImageKit
       Atlas       AI        Images
```

### Deployment Platforms

- **Frontend:** Vercel
- **Backend:** Render
- **Database:** MongoDB Atlas

The frontend communicates with the deployed backend using the `VITE_BASE_URL` environment variable.

## Security

- Passwords are hashed using bcrypt.
- JWT is used for user authentication.
- Protected routes use authentication middleware.
- Sensitive credentials are stored in environment variables.
- Database operations are handled through Mongoose.

## Future Enhancements

- More professional resume templates.
- Advanced ATS compatibility analysis.
- Resume scoring and keyword optimization.
- Multiple export formats.
- Additional AI-powered career and resume recommendations.

## Author

**Shrestha Gupta**

B.Tech – Electronics and Communication Engineering

Madan Mohan Malaviya University of Technology, Gorakhpur

- GitHub: https://github.com/Shrestha-Gupta
- LinkedIn: https://www.linkedin.com/in/shrestha01gupta/
- Portfolio: https://www.sadaaivgrow.in/

---

If you find this project useful, consider giving the repository a star!
