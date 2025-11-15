# Legal-Aid ECourt Scheduler — Analytics & Notification Manager

[![MERN Stack](https://img.shields.io/badge/Stack-MERN-green.svg)](https://www.mongodb.com/mern-stack)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

> A comprehensive analytics, notification, and communication management system for LegalAid Sri Lanka's online court hearing platform.

**Project Duration:** August 2025 – October 2025  
**Technology Stack:** MongoDB, Express.js, React.js, Node.js

---

## 📋 Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [System Architecture](#system-architecture)
- [Installation & Setup](#installation--setup)
- [Usage Guide](#usage-guide)
- [Project Structure](#project-structure)
- [Known Limitations](#known-limitations)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)

---

## 🎯 Overview

The **Legal-Aid ECourt Scheduler** is a MERN stack web application designed to streamline online court hearing management for LegalAid Sri Lanka. This repository contains the **Analytics & Notification Manager** module, which provides:

- Real-time operational dashboards and system metrics
- Comprehensive notification and announcement management
- Email communication tools with validation and tracking
- User feedback and review management
- Advanced analytics with exportable reports

### System Actors

- **Client** — End users requesting legal services
- **Lawyer** — Legal professionals managing cases
- **Finance Manager** — Financial operations oversight
- **Analytics & Notification Manager** — System administrator (this module)
- **Admin/System** — Platform administration

---

## ✨ Key Features

### 🔐 Authentication & Security
- Secure manager login with JWT-based authentication
- Protected dashboard routes with role-based access control

### 📊 Real-Time Dashboard
- Total system users, clients, and lawyers
- Active and completed case counts
- System performance status indicators
- Quick operational overview for decision-making

### 🔔 Notification Management
- Create and publish system-wide notifications
- Role-based notification targeting
- Complete notification history with sender tracking
- Audit trail for accountability and compliance

### 📢 Announcement System
- Create and publish announcements to user dashboards
- Immediate broadcast capabilities
- Role-specific announcement distribution
- Centralized communication hub

### 📧 Email Communication
- Compose and send emails with form validation
- Email format and required field verification
- Delivery tracking (sent count, response monitoring)
- Professional communication interface

### ⭐ Review Management
- View and respond to user feedback
- Dashboard metrics (average rating, resolution count)
- Feedback analysis and response tracking
- Quality assurance monitoring

### 📈 Analytics & Reporting
- Visual charts for case distribution and growth trends
- System usage analytics
- Exportable reports (CSV and PDF formats)
- Data-driven insights for stakeholders

### 👥 Development Workflow
- Git version control
- Agile methodology
- Collaborative team environment

---

## 🏗️ System Architecture

```
┌─────────────┐         ┌─────────────┐         ┌─────────────┐
│   React     │◄───────►│  Express    │◄───────►│  MongoDB    │
│  Frontend   │  REST   │   API       │  Mongoose│  Database   │
└─────────────┘   API   └─────────────┘         └─────────────┘
                              │
                              ▼
                        ┌──────────┐
                        │  Nodemailer │
                        │   (Email)   │
                        └──────────┘
```

---

## 🚀 Installation & Setup

### Prerequisites

- Node.js (v14 or higher)
- MongoDB (local or Atlas)
- npm or yarn package manager

### Installation Steps

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/legal-aid-ecourt-scheduler.git
cd legal-aid-ecourt-scheduler
```

2. **Install client dependencies**
```bash
cd client
npm install
```

3. **Install server dependencies**
```bash
cd ../server
npm install
```

4. **Configure environment variables**

Create a `.env` file in the `server` directory:

```env
# Server Configuration
PORT=5000
NODE_ENV=development

# Database
MONGO_URI=your_mongodb_connection_string

# Authentication
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRE=30d

# Email Configuration
EMAIL_USER=your_email@example.com
EMAIL_PASS=your_email_app_password
EMAIL_SERVICE=gmail
```

5. **Start the development servers**

**Backend:**
```bash
cd server
npm run dev
# Server runs on http://localhost:5000
```

**Frontend:**
```bash
cd client
npm start
# Client runs on http://localhost:3000
```

---

## 📖 Usage Guide

### Manager Login
1. Navigate to `http://localhost:3000`
2. Enter manager credentials
3. Access the protected dashboard

### Creating Notifications
1. Navigate to **Manage Notifications**
2. Fill in notification title and message
3. Select target roles
4. Submit to create notification
5. View notification history for audit trail

### Publishing Announcements
1. Go to **Manage Announcements**
2. Create announcement with title and content
3. Click **Publish** to broadcast to user dashboards

### Sending Emails
1. Navigate to **Compose Email**
2. Enter recipient email and message
3. System validates email format and required fields
4. Track sent emails and responses in dashboard

### Managing Reviews
1. Open **Manage Reviews**
2. View user feedback and ratings
3. Respond to reviews directly
4. Monitor average ratings and resolution metrics

### Generating Analytics
1. Access **Analytics** section
2. View interactive charts (case distribution, growth trends)
3. Export reports in CSV or PDF format
4. Share insights with stakeholders

---

## 📁 Project Structure

```
legal-aid-ecourt-scheduler/
├── client/                    # React frontend application
│   ├── public/
│   ├── src/
│   │   ├── components/       # Reusable React components
│   │   ├── pages/            # Page-level components
│   │   ├── services/         # API service functions
│   │   ├── utils/            # Utility functions
│   │   ├── App.js            # Main application component
│   │   └── index.js          # Application entry point
│   ├── package.json
│   └── .gitignore
│
├── server/                    # Express backend application
│   ├── controllers/          # Request handlers
│   ├── models/               # Mongoose schemas
│   ├── routes/               # API routes
│   ├── middleware/           # Custom middleware
│   ├── utils/                # Helper functions
│   ├── config/               # Configuration files
│   ├── server.js             # Server entry point
│   ├── package.json
│   └── .env                  # Environment variables
│
├── README.md                 # Project documentation
├── LICENSE                   # License information
└── .gitignore               # Git ignore rules
```

---

## ⚠️ Known Limitations

The following items are documented as planned improvements and are scheduled for the next development sprint:

### Email Delivery Tracking
- **Status:** In refinement
- **Description:** Email delivery logging currently tracks send attempts and successes. Bounce detection and failure categorization are under development.
- **Impact:** Non-critical; does not affect core email sending functionality
- **Timeline:** Scheduled for next sprint

### Announcement Clear Button
- **Status:** Minor front-end refinement needed
- **Description:** The clear button functionality requires a small UI adjustment
- **Impact:** Non-breaking; workaround available
- **Timeline:** Quick patch scheduled

### Browser Navigation Edge Case
- **Status:** Known routing behavior
- **Description:** Browser back/forward navigation may occasionally return to login screen
- **Impact:** Minimal; does not affect data integrity
- **Timeline:** Router configuration fix in progress

All limitations are tracked as issues in the project backlog and prioritized for resolution.

---

## 🔮 Future Enhancements

### Phase 1 (Next Sprint)
- ✅ Robust email delivery tracking with bounce handling
- ✅ Retry mechanism for failed email deliveries
- ✅ Enhanced announcement targeting with role-based queuing

### Phase 2
- 📱 Real-time push notifications using WebSocket integration
- 🧪 Comprehensive unit and integration test coverage
- 📊 Advanced analytics dashboard with predictive insights

### Phase 3
- 🔔 Mobile app notifications
- 🤖 Automated email templates and scheduling
- 📈 Machine learning-based trend analysis

---

## 🤝 Contributing

This project was developed as an academic demonstration using Agile methodologies and Git version control.

### Development Workflow
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👥 Team & Credits

**Developer:** Saranya Kirupananthan  
**Role:** Analytics & Notification Manager Module Lead

Developed collaboratively using Git version control and Agile project management practices.

---

## 📞 Support & Contact

For questions, issues, or contributions:
- 📧 Email: [kirupananthansaranya@gmail.com](mailto:kirupananthansaranya@gmail.com)
- 🐛 Issues: [GitHub Issues](https://github.com/SKSaranya-git/LegalAid-Sri-Lanka-ECourt-Schedule/issues)
- 📖 Documentation: [Project Saranya](https://github.com/SKSaranya-git/LegalAid-Sri-Lanka-ECourt-Schedule/Saranya)

---

**Built with ❤️ using the MERN Stack**
