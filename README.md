# 🏠 Hostel Hub - Complete Hostel Management System

A modern, full-stack hostel management web application with role-based authentication, real-time data management, and comprehensive CRUD operations.

![React](https://img.shields.io/badge/React-18.2.0-blue)
![Node.js](https://img.shields.io/badge/Node.js-Express-green)
![MongoDB](https://img.shields.io/badge/Database-MongoDB-brightgreen)
![Tailwind CSS](https://img.shields.io/badge/Styling-Tailwind%20CSS-38bdf8)

## 🌟 Features

### 🔐 Authentication & Authorization
- **Role-based access control** (Admin, Warden, Student)
- **JWT token authentication**
- **Separate login portals** for each role
- **Password hashing** with bcrypt
- **Protected routes** on frontend and backend

### 👨‍💼 Admin Dashboard
- View total students, rooms, and available beds
- Revenue tracking (total and pending)
- Complaint overview
- Occupancy rate calculation
- **Manage students** (Add, Edit, Delete)
- **Manage wardens** (Add, Edit, Delete, Assign Rooms)
- **Manage rooms** (Add, Edit, Delete)
- **Assign students to rooms**
- **Assign rooms to wardens**
- **Activity log** - Monitor all system activities
- Generate reports

### 👮 Warden Panel
- View assigned rooms only
- Update room status
- Manage all complaints
- Mark student attendance
- View dashboard statistics

### 🎓 Student Panel
- View personal profile
- View room details and roommates
- Check fee status and payment history
- Raise complaints
- Track complaint status
- View attendance records

### 🏠 Core Modules

#### Room Management
- Room number and block name
- Capacity tracking
- Occupied beds counter
- Available beds (auto-calculated)
- Status management (Available/Full/Maintenance)
- Warden assignment

#### Student Management
- Complete student profiles
- Personal and guardian information
- Course and year tracking
- Room assignment
- User account integration

#### Warden Management
- Add/Edit/Delete wardens
- Assign multiple rooms to wardens
- View assigned rooms
- Track warden activities

#### Payment Management
- Monthly fee structure
- Payment records with status
- Multiple payment methods
- Transaction ID tracking
- Payment history
- Revenue statistics

#### Complaint System
- Raise complaints with categories
- Status tracking (Pending/In Progress/Resolved)
- Categories (Maintenance, Food, Cleanliness, Security, Other)
- Resolution tracking

#### Attendance System
- Daily attendance marking
- Bulk attendance marking
- Status options (Present, Absent, Leave)
- Date-based filtering

#### Activity Log
- Track all system activities
- Filter by activity type
- Search functionality
- Real-time monitoring

## 🎨 UI/UX Features

### Modern SaaS Design
- Clean, professional interface
- Soft blue/teal color scheme
- Card-based layout
- Smooth animations and transitions
- Responsive design (mobile, tablet, desktop)

### Navigation
- Fixed sidebar navigation
- Top navbar with user profile
- Role-specific menu items
- Active route highlighting

### Components
- Reusable modal dialogs
- Stat cards with icons
- Data tables with search
- Form inputs with validation
- Badge components for status
- Loading spinners

## 🛠 Tech Stack

### Frontend
- **React 18** with Vite
- **Tailwind CSS** for styling
- **React Router DOM** for navigation
- **Axios** for API calls
- **Lucide React** for icons

### Backend
- **Node.js** & **Express.js**
- **MongoDB** with Mongoose ODM
- **JWT** for authentication
- **bcryptjs** for password hashing
- **CORS** enabled

## 📁 Project Structure

```
hostel-management-system/
├── server/                 # Backend application
│   ├── config/            # Database configuration
│   ├── controllers/       # Request handlers
│   ├── models/           # Database models
│   ├── routes/           # API routes
│   ├── middleware/       # Auth & error handling
│   ├── utils/            # Helper functions
│   └── server.js         # Entry point
├── client/               # Frontend application
│   ├── src/
│   │   ├── components/   # Reusable UI components
│   │   ├── pages/        # Page components
│   │   ├── context/      # React context (Auth)
│   │   ├── services/     # API service layer
│   │   └── utils/        # Helper functions
│   └── public/           # Static assets
└── docs/                 # Documentation
```

## 🚀 Installation & Setup

### Prerequisites
- Node.js (v16 or higher)
- MongoDB (local or Atlas)
- npm or yarn

### Backend Setup

1. Navigate to server directory:
```bash
cd server
npm install
```

2. Create `.env` file:
```bash
cp .env.example .env
```

3. Update `.env` with your configuration:
```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/hostel_hub
JWT_SECRET=your_jwt_secret_key_here
JWT_EXPIRE=7d
NODE_ENV=development
```

4. Seed the database (optional but recommended):
```bash
npm run seed
```

5. Start the server:
```bash
npm run dev
```

### Frontend Setup

1. Navigate to client directory:
```bash
cd client
npm install
```

2. Create `.env` file:
```bash
cp .env.example .env
```

3. Update `.env`:
```env
VITE_API_URL=http://localhost:5000/api
```

4. Start the development server:
```bash
npm run dev
```

## 🔑 Default Credentials

After running the seed script:

**Admin:**
- Email: `admin@hostel.com`
- Password: `admin123`

**Warden:**
- Email: `warden@hostel.com`
- Password: `warden123`

**Student:**
- Email: `john@student.com`
- Password: `student123`

## 📱 Access Points

- **Home Page**: http://localhost:3000
- **Admin Login**: http://localhost:3000/admin-login
- **Warden Login**: http://localhost:3000/warden-login
- **Student Login**: http://localhost:3000/login

## 🔌 API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user

### Students
- `GET /api/students` - Get all students
- `POST /api/students` - Create student
- `PUT /api/students/:id` - Update student
- `DELETE /api/students/:id` - Delete student
- `PUT /api/students/:id/assign-room` - Assign room

### Wardens
- `GET /api/auth/users?role=warden` - Get all wardens
- `POST /api/auth/register` - Create warden
- `PUT /api/auth/users/:id` - Update warden
- `DELETE /api/auth/users/:id` - Delete warden

### Rooms
- `GET /api/rooms` - Get all rooms
- `POST /api/rooms` - Create room
- `PUT /api/rooms/:id` - Update room
- `DELETE /api/rooms/:id` - Delete room

### Payments
- `GET /api/payments` - Get all payments
- `POST /api/payments` - Create payment
- `PUT /api/payments/:id` - Update payment
- `GET /api/payments/stats` - Get statistics

### Complaints
- `GET /api/complaints` - Get all complaints
- `POST /api/complaints` - Create complaint
- `PUT /api/complaints/:id` - Update complaint

### Attendance
- `GET /api/attendance` - Get attendance records
- `POST /api/attendance` - Mark attendance
- `POST /api/attendance/bulk` - Bulk mark attendance

### Dashboard
- `GET /api/dashboard/admin` - Admin dashboard stats
- `GET /api/dashboard/warden` - Warden dashboard stats
- `GET /api/dashboard/student/:id` - Student dashboard stats

## 🎯 Key Features Checklist

- ✅ Role-based authentication (Admin, Warden, Student)
- ✅ JWT token security
- ✅ Separate login portals for each role
- ✅ Admin dashboard with statistics
- ✅ Student management (CRUD)
- ✅ Warden management (CRUD)
- ✅ Room management (CRUD)
- ✅ Room assignment to students
- ✅ Room assignment to wardens
- ✅ Payment tracking
- ✅ Complaint system
- ✅ Attendance management
- ✅ Activity log
- ✅ Modern SaaS UI design
- ✅ Responsive layout
- ✅ Search and filter functionality
- ✅ Modal forms
- ✅ Loading states
- ✅ Error handling
- ✅ MongoDB persistence
- ✅ RESTful API architecture

## 🚢 Deployment

### Backend (Render/Railway)
1. Push code to GitHub
2. Connect repository to Render/Railway
3. Set environment variables
4. Deploy

### Frontend (Vercel/Netlify)
1. Build the project: `npm run build`
2. Deploy the `dist` folder
3. Set environment variables

### MongoDB Atlas (Cloud Database)
1. Create account on MongoDB Atlas
2. Create a new cluster (free tier available)
3. Create database user
4. Whitelist IP addresses
5. Get connection string
6. Update MONGODB_URI in backend

## 📚 Documentation

- [Quick Start Guide](QUICK_START.md)
- [Setup Guide](SETUP_GUIDE.md)
- [API Documentation](API_DOCUMENTATION.md)
- [Project Summary](PROJECT_SUMMARY.md)
- [Features Checklist](FEATURES_CHECKLIST.md)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License.

## 👨‍💻 Author

Created with ❤️ for modern hostel management

## 🙏 Acknowledgments

- React team for the amazing framework
- Tailwind CSS for the utility-first CSS framework
- MongoDB team for the database
- Express.js for the backend framework
- All open-source contributors

---

**⭐ Star this repository if you find it helpful!**

**🐛 Found a bug? Open an issue!**

**💡 Have a feature request? Let us know!**
