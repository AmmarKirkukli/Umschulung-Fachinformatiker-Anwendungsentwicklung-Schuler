# Umschulung Fachinformatiker Anwendungsentwicklung

A comprehensive web application for managing IT specialist training programs, seminars, and user subscriptions. Built with PHP and MySQL, featuring separate admin and user portals.

## 📋 Table of Contents

- [Features](#features)
- [Technologies](#technologies)
- [Requirements](#requirements)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Database Setup](#database-setup)
- [Usage](#usage)
- [Default Credentials](#default-credentials)
- [Screenshots](#screenshots)
- [Contributing](#contributing)
- [License](#license)

## ✨ Features

### Admin Portal
- 🔐 Secure admin authentication
- 👥 User management (view, edit, delete users)
- 📝 Seminar/Post management (create, edit, delete)
- 📊 Subscription tracking and management
- 📈 Dashboard with overview statistics
- 👤 Admin profile management

### User Portal
- 🔑 User registration and login
- 📚 Browse available seminars
- ✅ Subscribe to seminars
- 👤 User profile management
- 📝 Update personal information
- 🏠 Home page with program information

## 🛠 Technologies

### Backend
- **PHP** - Server-side scripting
- **MySQL/MariaDB** - Database management
- **PDO** - Database abstraction layer

### Frontend
- **HTML5** - Markup
- **CSS3** - Styling
- **Bootstrap 5.3** - Responsive framework
- **Font Awesome 6.4** - Icons
- **JavaScript** - Client-side interactivity

### Architecture
- **MVC Pattern** - Model-View-Controller architecture
- **Object-Oriented PHP** - Classes and objects

## 📦 Requirements

- **XAMPP** (or similar LAMP/WAMP stack)
  - PHP 7.4 or higher (tested with PHP 8.2.4)
  - MySQL 5.7 or higher / MariaDB 10.4 or higher
  - Apache Web Server
- **Web Browser** (Chrome, Firefox, Safari, Edge)

## 🚀 Installation

### 1. Clone or Download the Project

```bash
git clone https://github.com/AmmarKirkukli/Umschulung-Fachinformatiker-Anwendungsentwicklung.git
```

Or download and extract the ZIP file.

### 2. Move to XAMPP Directory

Move the project folder to your XAMPP htdocs directory:

```
C:\xampp\htdocs\Umschulung-Fachinformatiker-Anwendungsentwicklung
```

### 3. Start XAMPP

- Start **Apache** server
- Start **MySQL** server

### 4. Create Database

1. Open phpMyAdmin: `http://localhost/phpmyadmin`
2. Create a new database named: `Umschulung-Fachinformatiker-Anwendungsentwicklung`
3. Import the SQL file:
   - Navigate to the **Import** tab
   - Choose file: `admin/daten/Umschulung-Fachinformatiker-Anwendungsentwicklung.sql`
   - Click **Go**

### 5. Configure Database Connection

The database configuration is already set up in the following files:

**Admin Configuration:**
- File: `admin/model/config.php`
- File: `admin/model/Database.php`

**User Configuration:**
- File: `user/model/DatabaseUser.php`
- File: `user/model/dbh.cla.php`

Default settings:
```php
DB_HOST: 'localhost'
DB_NAME: 'Umschulung-Fachinformatiker-Anwendungsentwicklung'
DB_USER: 'root'
DB_PASSWORD: ''
```

If your MySQL credentials are different, update these files accordingly.

### 6. Access the Application

- **Main Page:** `http://localhost/Umschulung-Fachinformatiker-Anwendungsentwicklung/`
- **Admin Portal:** `http://localhost/Umschulung-Fachinformatiker-Anwendungsentwicklung/admin/`
- **User Portal:** `http://localhost/Umschulung-Fachinformatiker-Anwendungsentwicklung/user/`

## 📁 Project Structure

```
Umschulung-Fachinformatiker-Anwendungsentwicklung/
│
├── index.html                 # Main landing page (HTML)
├── index.php                  # Main landing page (PHP)
├── README.md                  # Project documentation
│
├── admin/                     # Admin portal
│   ├── index.php             # Admin entry point
│   ├── controller/           # Controllers (business logic)
│   │   ├── login_controller.php
│   │   ├── seminarController.php
│   │   ├── subscribeController.php
│   │   └── UserController.php
│   ├── model/                # Models (database interaction)
│   │   ├── admin_model.php
│   │   ├── config.php
│   │   ├── Database.php
│   │   ├── seminarModel.php
│   │   ├── subscribeModel.php
│   │   └── userModel.php
│   ├── view/                 # Views (presentation)
│   │   ├── homeAdmin.php
│   │   ├── login_view.php
│   │   ├── navbarAdmin.php
│   │   ├── profileAdmin.php
│   │   ├── seminar.php
│   │   ├── seminarNew.php
│   │   ├── subscribe_list.php
│   │   ├── user_list.php
│   │   ├── edit_user.php
│   │   └── editSeminar.php
│   ├── css/                  # Stylesheets
│   ├── js/                   # JavaScript files
│   ├── img/                  # Images
│   ├── daten/                # Database files
│   │   └── Umschulung-Fachinformatiker-Anwendungsentwicklung.sql
│   └── include/              # Includes
│       └── logoutAdmin.php
│
└── user/                      # User portal
    ├── index.php             # User entry point
    ├── model/                # Models
    │   ├── DatabaseUser.php
    │   ├── dbh.cla.php
    │   ├── login-contr.cla.php
    │   ├── login.class.php
    │   ├── signup-contr.cla.php
    │   ├── signup.class.php
    │   ├── updateUser-contr.cla.php
    │   ├── updateUser.class.php
    │   ├── seminarControllerUser.php
    │   ├── seminarModelUser.php
    │   └── Subscribe.php
    ├── view/                 # Views
    │   ├── home.php
    │   ├── navbar.php
    │   ├── footer.php
    │   ├── login1.php
    │   ├── register1.php
    │   ├── profile.php
    │   ├── updateUser.php
    │   ├── seminarUser.php
    │   ├── about.php
    │   ├── products.php
    │   └── team.php
    ├── include/              # Includes
    │   ├── login.inc.php
    │   ├── logout.inc.php
    │   ├── signup.inc.php
    │   └── updateUser.inc.php
    ├── css/                  # Stylesheets
    ├── js/                   # JavaScript files
    ├── img/                  # Images
    └── daten/                # Database files
```

## 🗄 Database Setup

### Database Tables

1. **admins** - Stores admin user credentials
   - admin_id (Primary Key)
   - username
   - password
   - email

2. **users** - Stores regular user credentials
   - user_id (Primary Key)
   - username
   - password
   - email

3. **posts** - Stores seminar/training information
   - post_id (Primary Key)
   - title
   - content
   - created_at

4. **subscriptions** - Links users to seminars
   - id (Primary Key)
   - user_id (Foreign Key)
   - post_id (Foreign Key)

## 📖 Usage

### For Administrators

1. Navigate to `http://localhost/Umschulung-Fachinformatiker-Anwendungsentwicklung/admin/`
2. Log in with admin credentials
3. Access the admin dashboard to:
   - Create, edit, or delete seminars
   - Manage user accounts
   - View and manage subscriptions
   - Update admin profile

### For Users

1. Navigate to `http://localhost/Umschulung-Fachinformatiker-Anwendungsentwicklung/user/`
2. Register a new account or log in
3. Browse available seminars
4. Subscribe to seminars of interest
5. Manage your profile and subscriptions

## 🔑 Default Credentials

### Admin Account
- **Username:** `ammar66`
- **Password:** `123123`
- **Email:** `ammarkirkukli@gmail.com`

⚠️ **Important:** Change these credentials after first login for security purposes!

## 📸 Screenshots

_(Add screenshots of your application here)_

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is created for educational purposes as part of the IT Specialist Application Development training program.

## 👨‍💻 Author

**Ammar Kirkukli**
- Email: ammarkirkukli@gmail.com
- GitHub: [@AmmarKirkukli](https://github.com/AmmarKirkukli)

## 🐛 Known Issues

- Passwords are stored in plain text (consider implementing password hashing with `password_hash()` and `password_verify()`)
- No CSRF protection implemented
- No input validation/sanitization in some forms
- SQL injection vulnerabilities may exist

## 🔐 Security Recommendations

For production use, consider implementing:

1. **Password Hashing** - Use `password_hash()` and `password_verify()`
2. **Prepared Statements** - Already partially implemented with PDO
3. **CSRF Protection** - Add tokens to forms
4. **Input Validation** - Sanitize all user inputs
5. **HTTPS** - Use SSL certificates
6. **Session Security** - Implement secure session handling
7. **Error Handling** - Hide sensitive error messages from users

## 📞 Support

For support, email ammarkirkukli@gmail.com or open an issue in the GitHub repository.

---

**Note:** This is a training project and should not be used in production without proper security enhancements.
