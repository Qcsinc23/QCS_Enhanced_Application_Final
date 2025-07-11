# QCS Event Management System

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://python.org)
[![Flask](https://img.shields.io/badge/Flask-2.3%2B-green.svg)](https://flask.palletsprojects.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Production%20Ready-brightgreen.svg)]()

A comprehensive event management system designed for Quality Control Specialists (QCS) to streamline event planning, inventory management, client coordination, and automated invoice generation.

## 🌟 Features

### 🎯 **Core Functionality**
- **Event Management** - Create, edit, and track events with advanced calendar integration
- **Client Management** - Centralized client database with communication history
- **Inventory Control** - Real-time equipment and supply tracking with low-stock alerts
- **Invoice Generation** - Automated billing with PDF export capabilities
- **User Authentication** - Role-based access control (Admin, Staff, Viewer)

### 🎨 **Enhanced User Experience**
- **Modern Landing Page** - Professional design with integrated login functionality
- **Responsive Dashboard** - Mobile-first design with comprehensive analytics
- **One-Click Event Completion** - Automatic invoice generation upon event completion
- **Calendar Integration** - Full calendar view with ICS import/export support
- **Dark Mode Support** - Toggle between light and dark themes

### 🔧 **Technical Features**
- **Blueprint Architecture** - Modular Flask application structure
- **RESTful API** - Well-documented API endpoints for all operations
- **Database Management** - SQLite with comprehensive schema design
- **Security** - CSRF protection, password hashing, and session management
- **PDF Generation** - WeasyPrint integration for professional invoices

## 🚀 Quick Start

### Prerequisites
- Python 3.9 or higher
- pip (Python package installer)
- Git

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/qcs-event-management.git
   cd qcs-event-management
   ```

2. **Set up virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r qcs_enhanced_final/requirements.txt
   ```

4. **Initialize the database**
   ```bash
   cd qcs_enhanced_final
   python init_db.py
   ```

5. **Run the application**
   ```bash
   python app.py
   ```

6. **Access the application**
   Open your browser and navigate to `http://localhost:5000`

### Default Login Credentials
- **Username:** admin
- **Password:** admin123
- **Role:** Administrator

> ⚠️ **Important:** Change the default credentials immediately after first login.

## 📁 Project Structure

```
qcs-event-management/
├── qcs_enhanced_final/           # Main application directory
│   ├── app.py                   # Flask application entry point
│   ├── config.py                # Configuration settings
│   ├── helpers.py               # Utility functions and decorators
│   ├── schema.sql               # Database schema
│   ├── requirements.txt         # Python dependencies
│   ├── blueprints/             # Modular application components
│   │   ├── calendar_bp.py      # Calendar and event management
│   │   ├── locations_bp.py     # Location management
│   │   └── tasks_bp.py         # Task management
│   ├── static/                 # Static assets
│   │   ├── style.css          # Main stylesheet
│   │   ├── script.js          # Core JavaScript
│   │   └── js/
│   │       └── calendar.js    # Calendar functionality
│   ├── templates/              # HTML templates
│   │   ├── layout.html        # Base template
│   │   ├── enhanced_landing.html # Modern landing page
│   │   ├── index.html         # Dashboard
│   │   └── [other templates]
│   ├── docs/                   # Documentation
│   │   ├── deployment_guide.md
│   │   └── [other docs]
│   └── scripts/                # Utility scripts
│       ├── setup.py
│       ├── backup.py
│       └── health_check.py
├── .gitignore                  # Git ignore rules
└── README.md                   # This file
```

## 🏗️ Architecture

### Technology Stack
- **Backend:** Python 3.9+ with Flask 2.3+
- **Database:** SQLite (easily upgradeable to PostgreSQL/MySQL)
- **Frontend:** HTML5, CSS3, JavaScript (ES6+), Bootstrap 5
- **Calendar:** FullCalendar.js integration
- **PDF Generation:** WeasyPrint
- **Authentication:** Flask-Session with PBKDF2 password hashing

### Design Patterns
- **Blueprint Architecture:** Modular application structure
- **MVC Pattern:** Clear separation of concerns
- **RESTful API:** Consistent API design
- **Responsive Design:** Mobile-first approach

## 📊 Key Components

### Event Management
- **Calendar View:** Interactive calendar with multiple view options
- **Event Creation:** Comprehensive event form with validation
- **Status Tracking:** Booked → In Progress → Completed workflow
- **Conflict Detection:** Automatic equipment and location conflict checking

### Inventory Management
- **Equipment Tracking:** Real-time availability monitoring
- **Kit Management:** Predefined equipment combinations
- **Low Stock Alerts:** Automated notifications for inventory thresholds
- **Assignment Tracking:** Equipment allocation per event

### Invoice System
- **Automatic Generation:** One-click invoice creation upon event completion
- **PDF Export:** Professional invoice templates
- **Payment Tracking:** Status monitoring (Paid/Unpaid)
- **Client Integration:** Automatic client information population

## 🔒 Security Features

- **Role-Based Access Control (RBAC)**
- **CSRF Protection**
- **Password Hashing** (PBKDF2 with salt)
- **Session Management**
- **Input Validation and Sanitization**
- **SQL Injection Prevention**

## 🧪 Testing

### Run Tests
```bash
cd qcs_enhanced_final
python -m pytest scripts/test.py -v
```

### Health Check
```bash
python scripts/health_check.py
```

## 📚 API Documentation

### Authentication Endpoints
- `POST /login` - User authentication
- `POST /logout` - User logout
- `POST /register` - User registration

### Event Management Endpoints
- `GET /api/events` - Retrieve events with filtering
- `POST /api/events` - Create new event
- `PUT /api/events/{id}` - Update event
- `DELETE /api/events/{id}` - Delete event
- `POST /api/events/{id}/complete` - Mark event complete with auto-invoice

### Calendar Integration
- `GET /export-calendar/ics` - Export calendar in ICS format
- `POST /import-calendar` - Import events from ICS file

## 🚀 Deployment

### Development
```bash
python app.py
```

### Production
For production deployment, use a WSGI server like Gunicorn:
```bash
pip install gunicorn
gunicorn -w 4 -b 0.0.0.0:5000 app:app
```

### Environment Variables
```bash
export FLASK_ENV=production
export SECRET_KEY=your-secret-key-here
export DATABASE_URL=your-database-url
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines
- Follow PEP 8 style guidelines
- Write comprehensive tests for new features
- Update documentation for API changes
- Use meaningful commit messages

## 📝 Changelog

### Version 2.0.0 (Current)
- ✅ Enhanced UX/UI with modern landing page
- ✅ Integrated login functionality in header
- ✅ One-click event completion with auto-invoice generation
- ✅ Improved logout flow returning to landing page
- ✅ Mobile-responsive design improvements
- ✅ Advanced calendar features

### Version 1.0.0
- Initial release with core functionality
- Basic event management
- Client and inventory systems
- User authentication

## 🐛 Known Issues

- WeasyPrint may require additional system dependencies for PDF generation
- Calendar export limited to standard ICS format
- Email notifications not yet implemented

## 📞 Support

For support, please:
1. Check the [documentation](docs/)
2. Search existing [issues](https://github.com/your-username/qcs-event-management/issues)
3. Create a new issue with detailed description

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Flask team for the excellent web framework
- FullCalendar.js for calendar functionality
- Bootstrap team for responsive design components
- WeasyPrint for PDF generation capabilities

---

**Built with ❤️ for Quality Control Specialists**

*QCS Event Management System - Streamlining professional event operations*