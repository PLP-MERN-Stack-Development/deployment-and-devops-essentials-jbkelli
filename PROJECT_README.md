# MERN Task Manager - Deployment & DevOps

A production-ready MERN stack application demonstrating deployment best practices, CI/CD pipelines, and DevOps essentials.

## 🚀 Live Demo

- **Frontend:** [Your Vercel URL]
- **Backend API:** https://mern-task-backend-2pj9.onrender.com
- **API Health:** https://mern-task-backend-2pj9.onrender.com/health

## 🎯 Features

- Full MERN stack (MongoDB, Express, React, Node.js)
- User authentication with JWT
- Task CRUD operations with validation
- Production-optimized build configuration
- Security headers and rate limiting
- Automated CI/CD with GitHub Actions
- Health check endpoints for monitoring
- Comprehensive error handling and logging

## 🛠️ Tech Stack

**Frontend:**
- React 18.3.1
- React Router 7.0.1
- Axios 1.7.7
- Vite 6.0.1

**Backend:**
- Node.js 18+
- Express 4.19.2
- MongoDB/Mongoose 8.7.2
- JWT Authentication
- bcryptjs for password hashing

**Security:**
- Helmet.js (HTTP security headers)
- CORS (cross-origin resource sharing)
- express-rate-limit (DDoS protection)
- express-validator (input validation)

**DevOps:**
- GitHub Actions (CI/CD)
- Render (backend hosting)
- Vercel (frontend hosting)
- MongoDB Atlas (database)

## 📁 Project Structure

```
deployment-and-devops-essentials-jbkelli/
├── client/                 # React frontend
│   ├── public/            # Static assets
│   ├── src/
│   │   ├── components/    # React components
│   │   ├── App.jsx        # Main app component
│   │   ├── App.css        # Styles
│   │   └── main.jsx       # Entry point
│   ├── .env               # Environment variables
│   ├── vite.config.js     # Vite configuration
│   ├── vercel.json        # Vercel deployment config
│   └── package.json       # Frontend dependencies
│
├── server/                # Express backend
│   ├── models/           # Mongoose models
│   │   ├── Task.js       # Task schema
│   │   └── User.js       # User schema
│   ├── routes/           # API routes
│   │   ├── tasks.js      # Task routes
│   │   └── users.js      # User/auth routes
│   ├── .env              # Environment variables
│   ├── server.js         # Express app
│   ├── render.yaml       # Render deployment config
│   └── package.json      # Backend dependencies
│
├── .github/
│   └── workflows/
│       └── ci-cd.yml     # GitHub Actions workflow
│
└── Documentation files (see below)
```

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- MongoDB Atlas account
- Git

### Local Development

1. **Clone the repository:**
   ```bash
   git clone <your-repo-url>
   cd deployment-and-devops-essentials-jbkelli
   ```

2. **Setup Backend:**
   ```bash
   cd server
   npm install
   # Copy .env.example to .env and update values
   npm run dev
   ```

3. **Setup Frontend:**
   ```bash
   cd client
   npm install
   # Copy .env.example to .env and update VITE_API_URL
   npm run dev
   ```

4. **Access the application:**
   - Frontend: http://localhost:3000
   - Backend: http://localhost:5000
   - Health Check: http://localhost:5000/health

## 🌐 Deployment

### Backend (Render)

1. Push code to GitHub
2. Connect repository to Render
3. Set root directory to `server`
4. Configure environment variables (see `RENDER_ENV_SETUP.md`)
5. Deploy!

**Detailed Guide:** See `DEPLOYMENT.md` or `RENDER_ENV_SETUP.md`

### Frontend (Vercel)

1. Push code to GitHub
2. Connect repository to Vercel
3. Set root directory to `client`
4. Set `VITE_API_URL` environment variable
5. Deploy!

**Detailed Guide:** See `VERCEL_DEPLOYMENT_GUIDE.md`

## 📚 Documentation

| File | Purpose |
|------|---------|
| `START_HERE.md` | Quick 5-step deployment checklist |
| `DEPLOYMENT.md` | Comprehensive deployment guide (482 lines) |
| `VERCEL_DEPLOYMENT_GUIDE.md` | Detailed Vercel setup |
| `RENDER_ENV_SETUP.md` | Backend environment configuration |
| `TROUBLESHOOTING.md` | Common issues and solutions |
| `QUICKSTART.md` | 5-minute local setup |
| `FINAL_REVIEW.md` | Complete project verification |

## 🔐 Environment Variables

### Backend (.env)
```env
NODE_ENV=production
PORT=5000
MONGODB_URI=<your-mongodb-atlas-uri>
CLIENT_URL=<your-frontend-url>
JWT_SECRET=<your-secret-key>
JWT_EXPIRE=7d
```

### Frontend (.env)
```env
VITE_API_URL=<your-backend-url>
VITE_APP_NAME=MERN Task Manager
VITE_APP_VERSION=1.0.0
```

## 🔒 Security Features

- **Helmet.js** - Secure HTTP headers
- **CORS** - Configured cross-origin requests
- **Rate Limiting** - 100 requests per 15 minutes
- **JWT Authentication** - Secure token-based auth
- **Password Hashing** - bcrypt with salt rounds
- **Input Validation** - express-validator on all routes
- **Environment Variables** - Sensitive data secured

## 📊 API Endpoints

### Public Endpoints
- `GET /` - API information
- `GET /health` - Health check
- `GET /api` - API status

### Tasks
- `GET /api/tasks` - Get all tasks (with pagination)
- `GET /api/tasks/:id` - Get task by ID
- `POST /api/tasks` - Create new task
- `PUT /api/tasks/:id` - Update task
- `DELETE /api/tasks/:id` - Delete task
- `PATCH /api/tasks/:id/complete` - Toggle completion

### Users (Authentication)
- `POST /api/users/register` - Register new user
- `POST /api/users/login` - Login user
- `GET /api/users/profile` - Get user profile
- `PUT /api/users/profile` - Update profile
- `DELETE /api/users/profile` - Delete account

## 🧪 Testing

```bash
# Backend tests
cd server
npm test

# Frontend build test
cd client
npm run build
```

## 📈 CI/CD Pipeline

GitHub Actions workflow includes:
- Backend testing and linting
- Frontend building and linting
- Automated deployment to Render (backend)
- Automated deployment to Vercel (frontend)

**Configuration:** `.github/workflows/ci-cd.yml`

## 🐛 Troubleshooting

### Common Issues

1. **API disconnected** - Check CORS configuration and backend URL
2. **Database not connected** - Verify MongoDB URI and network access
3. **Build fails** - Check Node version and dependencies
4. **CORS errors** - Update CLIENT_URL on backend

**Full Guide:** See `TROUBLESHOOTING.md`

## 📝 Assignment Completion

### Week 7 Requirements

- ✅ **Task 1:** Application preparation (optimization, env vars, security)
- ✅ **Task 2:** Backend deployment (Render with monitoring)
- ✅ **Task 3:** Frontend deployment (Vercel with optimization)
- ✅ **Task 4:** CI/CD pipeline (GitHub Actions)
- ✅ **Task 5:** Monitoring and maintenance (health checks, logging)

## 🤝 Contributing

This is an educational project for PLP Academy MERN Stack Development course.

## 📄 License

ISC

## 👨‍💻 Author

Created as part of PLP Academy Week 7 Assignment - Deployment and DevOps Essentials

## 🙏 Acknowledgments

- PLP Academy for the curriculum
- MongoDB Atlas for database hosting
- Render for backend hosting
- Vercel for frontend hosting

---

**Need Help?** Check the documentation files or see `TROUBLESHOOTING.md`

**Ready to Deploy?** Start with `START_HERE.md`

**Live Backend:** https://mern-task-backend-2pj9.onrender.com
