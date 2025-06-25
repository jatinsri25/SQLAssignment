# MERN Stack Task Manager (SQL Edition)

A full-stack task management application built with React.js, Node.js, Express, and MySQL using Sequelize ORM.

## Features

- **User Authentication**: Sign up and login with JWT authentication
- **Task Management**: Create, view, and update tasks
- **Status Tracking**: Tasks flow from "To Do" → "In Progress" → "Done"
- **Modern UI**: Beautiful gradient design with smooth animations and hover effects
- **Responsive Design**: Works perfectly on desktop and mobile devices
- **Real-time Updates**: Tasks update immediately in the UI

## Tech Stack

### Backend
- **Node.js** with Express.js
- **MySQL** database
- **Sequelize** ORM
- **JWT** for authentication
- **bcryptjs** for password hashing
- **CORS** for cross-origin requests

### Frontend
- **React.js** with functional components and hooks
- **React Router** for navigation
- **Axios** for API calls
- **Custom CSS** with modern design patterns
- **Context API** for state management

## Prerequisites

- Node.js (v14 or higher)
- MySQL (v8.0 or higher)
- npm or yarn

## Installation & Setup

### 1. Clone the repository
```bash
git clone <repository-url>
cd SQL-Assignment
```

### 2. Database Setup
Make sure MySQL is running and create the database:
```sql
CREATE DATABASE task_manager_dev;
```

### 3. Backend Setup
```bash
cd backend

# Install dependencies
npm install

# Update database configuration
# Edit config/config.json with your MySQL credentials

# Run database migrations
npx sequelize-cli db:migrate

# Start the development server
npm run dev
```

The backend will run on `http://localhost:5001`

### 4. Frontend Setup
```bash
cd frontend

# Install dependencies
npm install

# Start the development server
npm start
```

The frontend will run on `http://localhost:3000` (or 3003 if 3000 is busy)

## API Endpoints

### Authentication
- `POST /api/signup` - Register a new user
- `POST /api/login` - Login user

### Tasks (Protected Routes)
- `GET /api/tasks` - Get all tasks for authenticated user
- `POST /api/tasks` - Create a new task
- `PUT /api/tasks/:id` - Update a task
- `DELETE /api/tasks/:id` - Delete a task (bonus feature)

## Database Schema

### Users Table
- `id` (Primary Key)
- `name` (String, required)
- `email` (String, unique, required)
- `password` (String, hashed, required)
- `createdAt` (Timestamp)
- `updatedAt` (Timestamp)

### Tasks Table
- `id` (Primary Key)
- `title` (String, required)
- `status` (ENUM: 'To Do', 'In Progress', 'Done', default: 'To Do')
- `user_id` (Foreign Key to Users.id)
- `createdAt` (Timestamp)
- `updatedAt` (Timestamp)

## Usage

1. **Sign Up**: Create a new account with your name, email, and password
2. **Login**: Sign in with your credentials
3. **Add Tasks**: Use the form at the top to add new tasks
4. **Manage Tasks**: View tasks grouped by status and update their progress
5. **Status Flow**: Tasks automatically flow from "To Do" → "In Progress" → "Done"

## UI Features

- **Gradient Background**: Beautiful purple gradient background
- **Glass Morphism**: Semi-transparent cards with backdrop blur
- **Smooth Animations**: Hover effects and transitions throughout
- **Loading States**: Spinner animations for better UX
- **Status Badges**: Color-coded task status indicators
- **Responsive Grid**: Adapts to different screen sizes
- **Modern Forms**: Enhanced input styling with focus states

## Project Structure

```
SQL-Assignment/
├── backend/
│   ├── config/
│   │   └── config.json
│   ├── models/
│   │   ├── user.js
│   │   └── task.js
│   ├── migrations/
│   ├── server.js
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Login.js
│   │   │   ├── Signup.js
│   │   │   └── Dashboard.js
│   │   ├── context/
│   │   │   └── AuthContext.js
│   │   ├── App.js
│   │   └── index.js
│   └── package.json
└── README.md
```

## Environment Variables

Create a `.env` file in the backend directory:
```env
JWT_SECRET=your-secret-key-here
PORT=5001
```

## Deployment

### Backend (Render/Vercel)
1. Set environment variables
2. Configure database connection
3. Deploy using the platform's CLI or dashboard

### Frontend (Vercel/Netlify)
1. Update API base URL to production backend URL
2. Deploy using the platform's CLI or dashboard

## Bonus Features Implemented

- ✅ Task deletion functionality
- ✅ Modern, responsive design with gradients and animations
- ✅ Enhanced user experience with loading states
- ✅ Clean and intuitive interface
- ✅ Error handling and success messages
- ✅ Protected routes with authentication
- ✅ Smooth hover effects and transitions

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is open source and available under the [MIT License](LICENSE). 