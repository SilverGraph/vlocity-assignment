---

## 🖥️ Frontend

The frontend is built with **React.js** and styled using **Material UI (MUI)** components. It communicates with the backend via RESTful APIs and handles authentication with JWT tokens stored in Redux and `localStorage`.

### 🔑 Features

- Role-based authentication (Admin / User)
- Dashboard with projects and issues
- Filter issues by status, priority, or assignee
- Admin can create projects and assign to users
- Admin can also create tickets and assign it to users
- User can view assigned issues and projects

### 🧭 Routes

| Route           | Component         | Description                       |
|------------------|-------------------|-----------------------------------|
| `/login`         | `LoginPage`       | Login form                        |
| `/register`      | `SignupPage`      | Register as User/Admin            |
| `/dashboard`     | `DashboardPage`   | Admin or User dashboard view      |
| `/projects/:id`  | `ProjectDetails`  | View details of a project         |
| `/issues`        | `ViewIssues`      | View and filter all issues        |
| `/create-issue`  | `IssueForm`       | Create new issue (Admin only)     |

---

## 🚀 Deployment

- **Frontend**: Deployed on [Netlify](https://www.netlify.com/)
- **Backend**: Suggested options include [Render](https://render.com/), [Railway](https://railway.app/), or [Vercel Serverless Functions](https://vercel.com/)

## 📚 API Documentation

### 🔐 Auth Routes

| Method | Route                | Description                      | Access  |
|--------|----------------------|----------------------------------|---------|
| POST   | `/api/auth/register` | Register new user (admin or user)| Public  |
| POST   | `/api/auth/login`    | Login user and return token      | Public  |

---

### 👤 Backend

| Method | Route      | Description                    | Access     |
|--------|------------|--------------------------------|------------|
| GET    | `/api/users` | Get all users with role "user" | Admin only |

---

### 🗂️ Project Routes

| Method | Route               | Description        | Access     |
|--------|---------------------|--------------------|------------|
| POST   | `/api/projects`     | Create new project | Admin only |
| GET    | `/api/projects`     | Get all projects   | Admin/User |

---

### 🐛 Issue Routes

| Method | Route              | Description         | Access     |
|--------|--------------------|---------------------|------------|
| POST   | `/api/issues`      | Create new issue    | Admin only |
| GET    | `/api/issues`      | Get all issues      | Admin/User |
| GET    | `/api/issues/:id`  | Get issue by ID     | Admin/User |

---

### 📊 Dashboard Route

| Method | Route                  | Description                            | Access     |
|--------|------------------------|----------------------------------------|------------|
| GET    | `/api/dashboard/admin` | Get all projects & issues (Admin view) | Admin only |
| GET    | `/api/dashboard/user`  | Get assigned projects & issues         | User only  |

## 🔧 Setup Instructions

### Backend

1. **Install dependencies**  
   Navigate to the backend directory and run:
   ```bash
   npm install
2. **Create a .env file in the root of the backend with the following:**
  ```
  PORT=5000
  MONGO_URI=your_mongodb_connection_string
  JWT_SECRET=your_secret_key
  ```
3. **Start the backend server**  
   Navigate to the backend directory and run:
   ```bash
   npm run dev

### Frontend

1. **Navigate to the frontend directory**  
   ```bash
   cd frontend
2. **Install dependencies**  
   ```bash
   npm install
3. **Create a .env file in the root of the frontend folder and add:**
   ```bash
   REACT_APP_API_BASE_URL=http://localhost:5000/api
4. **Start the frontend**  
   Navigate to the frontend directory and run:
   ```bash
   npm start
