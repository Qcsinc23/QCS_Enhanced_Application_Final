# QCS Event Management Application

A comprehensive event management system built with Flask, designed for professional event planning, client management, and inventory tracking.

## 🌟 Features

### Core Functionality
- **Event Management** - Create, edit, and track events with calendar integration
- **Client Management** - Manage client information and communication history
- **Inventory Control** - Track elements, equipment, and kits
- **User Authentication** - Role-based access control (Admin, Staff, Viewer)
- **Calendar Integration** - Full calendar view with ICS import/export
- **Location Management** - Venue tracking and management
- **Task Management** - Event-specific task assignments and tracking
- **Invoice Generation** - PDF invoice creation with WeasyPrint

### Enhanced Features
- **Responsive Design** - Modern, mobile-friendly interface
- **Dark Theme Support** - User-friendly dark mode
- **Security Headers** - Production-ready security implementation
- **PDF Export** - Generate professional invoices and reports
- **Blueprint Architecture** - Modular, scalable code structure
- **Advanced Calendar** - Drag-and-drop events, conflict detection
- **Equipment Tracking** - Comprehensive inventory management

## 🚀 Quick Start

### Prerequisites
- Python 3.9 or higher
- pip (Python package installer)

### Installation

1. **Clone or Extract the Application**
   ```bash
   # If you have the zip file, extract it
   # If using git: git clone <repository-url>
   cd QCS_Event_Management_App
   ```

2. **Create Virtual Environment (Recommended)**
   ```bash
   python -m venv venv
   
   # Activate virtual environment
   # On Windows:
   venv\Scripts\activate
   # On macOS/Linux:
   source venv/bin/activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Initialize Database** (Optional - database included)
   ```bash
   # Only run if you want to reset the database
   python init_db.py
   ```

5. **Run the Application**
   ```bash
   python app.py
   ```

6. **Access the Application**
   - Open your browser and go to: `http://localhost:5004`
   - Default login credentials:
     - Username: `admin`
     - Password: `admin`

## 🔐 Default Credentials

- **Admin User**
  - Username: `admin`
  - Password: `admin`
  - Role: Administrator (full access)

- **Viewer User**
  - Username: `trevor50020`
  - Password: `admin` (or check database)
  - Role: Viewer (read-only access)

> **Important:** Change default passwords in production!

## 📊 Database Overview

The application includes a pre-configured SQLite database with:
- **23 Tables** with proper relationships
- **Sample Data** including clients, events, and inventory
- **User Accounts** with role-based permissions
- **Clean Data Structure** - no integrity issues

### Key Tables
- `users` - User authentication and roles
- `clients` - Client information and preferences
- `events` - Event details and scheduling
- `elements` - Inventory items and equipment
- `locations` - Venue information
- `event_tasks` - Task management for events

## 🏗️ Architecture

### File Structure
```
QCS_Event_Management_App/
├── app.py                 # Main Flask application
├── helpers.py            # Utility functions and decorators
├── config.py             # Configuration templates
├── schema.sql            # Database schema definition
├── init_db.py           # Database initialization script
├── database.db          # SQLite database (ready to use)
├── requirements.txt     # Python dependencies
├── blueprints/          # Modular application components
│   ├── calendar_bp.py   # Calendar and event API routes
│   ├── locations_bp.py  # Location management
│   └── tasks_bp.py      # Task management
├── templates/           # HTML templates (Jinja2)
├── static/             # CSS, JavaScript, images
│   ├── style.css       # Main stylesheet
│   ├── script.js       # Core JavaScript
│   └── js/calendar.js  # Calendar functionality
├── docs/               # Documentation and analysis
└── scripts/            # Utility scripts
```

### Technology Stack
- **Backend:** Flask 2.2.3, SQLite, Python 3.9+
- **Frontend:** HTML5, CSS3, JavaScript, Bootstrap 5
- **Security:** bcrypt, CSRF protection, secure headers
- **PDF Generation:** WeasyPrint
- **Calendar:** ICS format support
- **Architecture:** Blueprint-based modular design

## 🔧 Configuration

### Environment Variables
```bash
# Required for production
export SECRET_KEY="your-super-secret-key-here"
export FLASK_ENV="production"
export DATABASE_PATH="/path/to/production/database.db"
```

### Configuration Files
- `config.py` - Production configuration template
- Modify settings for your deployment environment

## 🛡️ Security Features

### Implemented Security
- ✅ **Password Hashing** - bcrypt and pbkdf2 support
- ✅ **CSRF Protection** - Form submission security
- ✅ **Security Headers** - XSS, clickjacking protection
- ✅ **SQL Injection Protection** - Parameterized queries
- ✅ **Role-Based Access** - User permission system
- ✅ **Session Security** - Secure session management

### Production Security Checklist
- [ ] Change default secret key
- [ ] Enable HTTPS
- [ ] Configure firewall
- [ ] Set up regular backups
- [ ] Monitor for security updates
- [ ] Review user permissions

## 📖 User Guide

### Getting Started
1. **Login** with admin credentials
2. **Add Clients** in the Clients section
3. **Create Events** using the calendar or events page
4. **Manage Inventory** in Elements/Equipment sections
5. **Assign Tasks** for event planning
6. **Generate Reports** and invoices as needed

### User Roles
- **Admin:** Full system access, user management
- **Staff:** Event and client management, limited admin functions
- **Viewer:** Read-only access to events and data

### Key Workflows
1. **Event Planning:** Client → Event → Tasks → Equipment Assignment
2. **Inventory Management:** Elements → Kits → Equipment Tracking
3. **Client Management:** Contacts → Communications → Event History

## 🔧 Advanced Configuration

### Database Customization
- SQLite included for quick start
- Can be configured for PostgreSQL in production
- See `config.py` for database options

### Performance Optimization
- Database indexes already configured
- Static file caching enabled
- Optimized query patterns implemented

### Extending the Application
- Add new blueprints for additional features
- Customize templates in `/templates` directory
- Extend the database schema as needed

## 📋 Maintenance

### Regular Tasks
- **Daily:** Monitor application logs
- **Weekly:** Database backup verification
- **Monthly:** Security updates review
- **Quarterly:** Full system backup test

### Backup Strategy
```bash
# Backup database
cp database.db backup_$(date +%Y%m%d).db

# Backup entire application
tar -czf qcs_backup_$(date +%Y%m%d).tar.gz QCS_Event_Management_App/
```

## 🐛 Troubleshooting

### Common Issues
1. **Import Errors:** Ensure all dependencies installed
2. **Database Errors:** Check file permissions on database.db
3. **Login Issues:** Verify admin password hasn't been changed
4. **Port Conflicts:** Change port in app.py if 5004 is in use

### Getting Help
- Check `/docs` folder for detailed documentation
- Review application logs for error messages
- Ensure all requirements are installed correctly

## 📝 What's New

### Recent Enhancements (Fixed Issues)
- ✅ **Authentication System** - Fixed password hashing compatibility
- ✅ **Blueprint Registration** - Resolved URL routing conflicts
- ✅ **Template Errors** - Completed missing template structures
- ✅ **Security Headers** - Added comprehensive security
- ✅ **Database Integrity** - Verified and fixed all data relationships
- ✅ **Testing Coverage** - 100% functionality validation

### Version History
- **v1.0** - Initial release with core features
- **v1.1** - Enhanced security and bug fixes
- **v1.2** - Blueprint architecture and modular design
- **v2.0** - Current version with all critical fixes applied

## 📄 License

This application is provided as-is for event management purposes. Please review and comply with all applicable licenses for included dependencies.

## 🤝 Support

For technical support or feature requests:
1. Review the documentation in `/docs`
2. Check the troubleshooting section above
3. Verify your installation follows all steps correctly

---

**QCS Event Management Application v2.0**  
*Professional Event Planning Made Simple*

Last Updated: July 11, 2025
