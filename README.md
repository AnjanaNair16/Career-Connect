# CareerConnect

CareerConnect is a MERN-stack job portal that connects employers with job seekers. Employers can post jobs and manage applicants, while job seekers can browse listings, apply, and track their applications.

## Features

### 👤 User Accounts
- Register & Login with JWT authentication
- Role-based access control (Job Seeker / Employer)

### 💼 For Employers
- Post new job listings
- Edit or delete posted jobs
- View applications from job seekers

### 📄 For Job Seekers
- Browse available jobs
- View job details
- Apply with resume upload (Cloudinary storage)
- View and delete submitted applications

## Tech Stack

### Frontend
- React (Context API + Router)
- Axios
- react-hot-toast

### Backend
- Node.js + Express
- MongoDB + Mongoose
- JWT + bcrypt
- Cloudinary (resume storage)

---

## Folder Structure

```
CareerConnect/
 ├── backend/
 │   ├── controllers/
 │   ├── models/
 │   ├── routes/
 │   ├── database/
 │   ├── middlewares/
 │   ├── utils/
 │   ├── app.js
 │   └── server.js
 └── frontend/
     ├── node_modules/
     ├── public/
     ├── src/
     │   ├── components/
     │   │   ├── Application/
     │   │   ├── Auth/
     │   │   ├── Home/
     │   │   ├── Job/
     │   │   ├── Layout/
     │   │   └── NotFound/
     │   ├── App.css
     │   ├── App.jsx
     │   └── main.jsx
     ├── index.html
     └── .eslintrc.cjs

```

---

## Environment Variables

### Backend `.env` example:
```
PORT=4000
DB_URL=mongodb://localhost:27017
JWT_SECRET_KEY=your_jwt_secret
JWT_EXPIRE=5d

CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

FRONTEND_URL=http://localhost:5173
```

---

## Installation

### 1. Clone the repository
```bash
git clone <repo-link>
cd CareerConnect
```

### 2. Backend Setup
```bash
cd backend
npm install
npm run dev
```

### 3. Frontend Setup
```bash
cd ../frontend
npm install
npm run dev
```

---

## API Endpoints

### User Routes
```
POST /api/v1/user/register
POST /api/v1/user/login
GET  /api/v1/user/logout
GET  /api/v1/user/getuser
```

### Job Routes
```
GET    /api/v1/job/getall
POST   /api/v1/job/post
GET    /api/v1/job/getmyjobs
PUT    /api/v1/job/update/:id
DELETE /api/v1/job/delete/:id
GET    /api/v1/job/:id
```

### Application Routes
```
POST   /api/v1/application/post
GET    /api/v1/application/employer/getall
GET    /api/v1/application/jobseeker/getall
DELETE /api/v1/application/delete/:id
```

---

## Authentication Flow

- Login sets a JWT token in an HTTP-only cookie
- Protected routes use `isAuthenticated`
- Roles enforce Job Seeker vs Employer behavior

---

## Resume Upload Handling

- Only PNG/JPEG/WEBP formats allowed
- Cloudinary handles storage & secure URL delivery
- Frontend shows resume preview in modal

---

## Future Enhancements

- PDF support for resumes
- Job filters & search
- Pagination
- Email notifications
- Company profile pages




