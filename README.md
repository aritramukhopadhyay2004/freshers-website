# 🎓 ABHIGRAHA 2K25 — Freshers Website

<div align="center">

[![Node.js](https://img.shields.io/badge/Node.js-v18.0+-339933?style=flat-square&logo=node.js)](https://nodejs.org/)
[![React](https://img.shields.io/badge/React-19.1.1-61DAFB?style=flat-square&logo=react)](https://react.dev/)
[![Express](https://img.shields.io/badge/Express-4.18.2-000000?style=flat-square&logo=express)](https://expressjs.com/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=flat-square&logo=postgresql)](https://www.postgresql.org/)
[![Vite](https://img.shields.io/badge/Vite-7.1.2-646CFF?style=flat-square&logo=vite)](https://vitejs.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-3.4.13-06B6D4?style=flat-square&logo=tailwind-css)](https://tailwindcss.com/)
[![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)](LICENSE)

**A modern, full-stack web application for managing freshers orientation events with real-time updates, admin dashboard, and comprehensive event management features.**

[📖 Documentation](#features) • [🚀 Quick Start](#quick-start) • [📁 Project Structure](#project-structure) • [🛠️ Tech Stack](#tech-stack)

</div>

---

## ✨ Features

### 🎯 Core Functionality
- **Event Management** - Create, update, and manage freshers orientation events
- **Admin Dashboard** - Comprehensive admin panel for event and user management
- **User Authentication** - Secure JWT-based authentication with role-based access control
- **File Upload Support** - Seamless file upload capabilities with Multer
- **Real-time Updates** - Responsive frontend with React and Vite
- **Modern UI** - Beautiful, responsive design using Tailwind CSS
- **API Analytics** - Integrated Vercel Analytics for performance tracking

### 🔐 Security Features
- Password hashing with bcryptjs
- JWT-based authentication
- CORS enabled
- Environment variable management
- Role-based access control (RBAC)

### 📱 Responsive Design
- Mobile-first approach
- Fully responsive UI components
- Progressive web app ready

---

## 🚀 Quick Start

### Prerequisites
- Node.js (v18.0 or higher)
- PostgreSQL (v12 or higher)
- npm or yarn package manager

### Installation

#### Clone the Repository
```bash
git clone https://github.com/aritramukhopadhyay2004/freshers-website.git
cd freshers-website
```

#### Frontend Setup
```bash
cd frontend
npm install
npm run dev      # Start development server
# or
npm run build    # Build for production
```

#### Backend Setup
```bash
cd ../backend
npm install

# Create a .env file
echo "DATABASE_URL=postgresql://user:password@localhost:5432/freshers_db" > .env
echo "JWT_SECRET=your_secret_key_here" >> .env
echo "PORT=5000" >> .env

npm run dev      # Start development server with nodemon
# or
npm start        # Start production server
```

#### Initialize Database
```bash
# Create admin user
cd backend
npm run create-admin

# Seed sample data
npm run seed-sample
```

---

## 📁 Project Structure

```
freshers-website/
├── 📦 backend/
│   ├── 📁 routes/
│   │   ├── admin.js          # Admin endpoints
│   │   ├── auth.js           # Authentication endpoints
│   │   └── public.js         # Public/General endpoints
│   ├── 📁 middleware/        # Authentication & validation middleware
│   ├── 📁 models/            # Sequelize database models
│   ├── 📁 migrations/        # Database migrations
│   ├── 📁 scripts/           # Utility scripts
│   ├── 📁 instance/          # Database instance config
│   ├── app.js                # Express server entry point
│   └── package.json
│
├── 📦 frontend/
│   └── 📁 src/
│       ├── 📁 admin/         # Admin dashboard components
│       ├── 📁 components/    # Reusable React components
│       ├── 📁 pages/         # Page components
│       ├── 📁 assets/        # Images, icons, styles
│       ├── 📁 config/        # Configuration files
│       ├── App.jsx
│       └── main.jsx
│
├── package.json              # Root dependencies (if any)
├── package-lock.json
├── README.md                 # This file
└── .gitignore
```

---

## 🛠️ Tech Stack

### Frontend
| Technology | Version | Purpose |
|------------|---------|----------|
| **React** | ^19.1.1 | UI library |
| **Vite** | ^7.1.2 | Build tool & dev server |
| **React Router** | ^7.8.2 | Client-side routing |
| **Tailwind CSS** | ^3.4.13 | Styling & responsive design |
| **ESLint** | ^9.33.0 | Code quality |
| **PostCSS** | ^8.5.6 | CSS transformation |
| **Vercel Analytics** | ^1.4.1 | Performance tracking |

### Backend
| Technology | Version | Purpose |
|------------|---------|----------|
| **Express.js** | ^4.18.2 | Web framework |
| **PostgreSQL** | (via Sequelize) | Database |
| **Sequelize** | ^6.32.1 | ORM |
| **JWT** | ^9.0.2 | Authentication |
| **bcryptjs** | ^2.4.3 | Password hashing |
| **Multer** | ^1.4.5 | File uploads |
| **CORS** | ^2.8.5 | Cross-origin requests |
| **Nodemon** | ^3.0.1 | Dev auto-reload |
| **dotenv** | ^16.3.1 | Environment variables |

---

## 🔌 API Endpoints

### Authentication Routes (`/api/auth`)
- `POST /login` - User login
- `POST /register` - User registration
- `POST /logout` - User logout
- `POST /refresh` - Refresh JWT token

### Public Routes (`/api/public`)
- `GET /events` - Get all public events
- `GET /events/:id` - Get event details
- `GET /about` - Get event information

### Admin Routes (`/api/admin`) - ⚠️ Requires Authentication
- `POST /events` - Create new event
- `PUT /events/:id` - Update event
- `DELETE /events/:id` - Delete event
- `GET /dashboard` - Admin dashboard stats
- `GET /users` - Manage users
- `POST /uploads` - Handle file uploads

---

## 📝 Environment Variables

### Backend (.env)
```env
# Database Configuration
DATABASE_URL=postgresql://user:password@localhost:5432/freshers_db

# JWT Configuration
JWT_SECRET=your_super_secret_jwt_key_here
JWT_EXPIRY=7d

# Server Configuration
PORT=5000
NODE_ENV=development

# CORS
CORS_ORIGIN=http://localhost:5173
```

### Frontend (.env)
```env
VITE_API_URL=http://localhost:5000/api
```

---

## 🚦 Running the Application

### Development Mode
```bash
# Terminal 1 - Backend
cd backend
npm run dev

# Terminal 2 - Frontend
cd frontend
npm run dev
```

Frontend will run at: `http://localhost:5173`
Backend API will run at: `http://localhost:5000`

### Production Build
```bash
# Frontend
cd frontend
npm run build
npm run preview

# Backend
cd backend
npm start
```

---

## 🗺️ Roadmap

- [ ] Admin dashboard UI polish and analytics enhancements
- [ ] Rich text editor for event descriptions
- [ ] Media upload with progress tracking and moderation
- [ ] Push notifications and RSVP integration
- [ ] Internationalization (i18n) support
- [ ] Accessibility audit and WCAG compliance
- [ ] Email notifications system
- [ ] Event calendar integration
- [ ] QR code generation for events
- [ ] Real-time participant count updates

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

### Commit Convention
Use conventional commits for clear history:
- `feat:` New feature
- `fix:` Bug fix
- `docs:` Documentation changes
- `style:` Code style changes
- `refactor:` Code refactoring
- `test:` Test additions/changes
- `chore:` Dependency/config changes

---

## 👥 Team & Contributors

<div align="center">

### 👨‍💻 **Developer & DevOps**
**Arpan Pramanik** ([@arpanpramanik2003](https://github.com/arpanpramanik2003))

*Full-stack development, backend architecture, DevOps infrastructure, and system administration*

---

### 🎨 **UI/UX Designer & Operation, Management**
**Aritra Mukhopadhyay** ([@aritramukhopadhyay2004](https://github.com/aritramukhopadhyay2004))

*User interface design, user experience optimization, and project operations*

</div>

---

## 🔒 Security

Security is a top priority. Please follow these guidelines:

### Reporting Vulnerabilities
- **DO NOT** create public issues for security vulnerabilities
- Report privately via GitHub Security Advisory
- Include steps to reproduce and potential impact
- Allow reasonable time for a fix before disclosure

### Security Best Practices
- Never commit secrets or API keys to the repository
- Use `.env` files for sensitive configuration (included in `.gitignore`)
- Rotate keys and tokens regularly
- Enforce least privilege on database and API access
- Keep dependencies updated (`npm audit`, `npm update`)
- Use HTTPS in production
- Validate and sanitize all user inputs

---

## 📊 Project Statistics

![GitHub commit activity](https://img.shields.io/github/commit-activity/m/aritramukhopadhyay2004/freshers-website?style=flat-square&label=commits)
![GitHub issues](https://img.shields.io/github/issues/aritramukhopadhyay2004/freshers-website?style=flat-square&label=issues)
![GitHub pull requests](https://img.shields.io/github/issues-pr/aritramukhopadhyay2004/freshers-website?style=flat-square&label=pull%20requests)
![GitHub repo size](https://img.shields.io/github/repo-size/aritramukhopadhyay2004/freshers-website?style=flat-square)

---

## 📚 Resources & Documentation

- [React Documentation](https://react.dev/)
- [Express.js Guide](https://expressjs.com/)
- [Sequelize ORM](https://sequelize.org/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Vite Guide](https://vitejs.dev/)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)

---

## 💬 Support & Questions

- **Issues**: [GitHub Issues](https://github.com/aritramukhopadhyay2004/freshers-website/issues)
- **Discussions**: [GitHub Discussions](https://github.com/aritramukhopadhyay2004/freshers-website/discussions)
- **Email**: Contact the team directly

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

### License Summary
- ✅ You can use this code commercially
- ✅ You can modify the code
- ✅ You can distribute the code
- ⚠️ You must include the license and copyright notice
- ❌ The code is provided "as-is" without warranty

---

## 🙏 Acknowledgments

- **ABHIGRAHA 2K25** organizing committee
- **All contributors and volunteers** who made this project possible
- **Open source community** for amazing tools and libraries
- **React**, **Express.js**, **PostgreSQL**, **Tailwind CSS** communities

---

<div align="center">

**Built with ❤️ for ABHIGRAHA 2K25**

[⬆ Back to Top](#-abhigraha-2k25--freshers-website)

</div>
