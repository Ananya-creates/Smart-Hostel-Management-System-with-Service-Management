# Hostel Management System

A complete, secure web-based Hostel Management portal built with **PHP, MySQL, and Vanilla JavaScript**. It features separate dashboards for Admins (Wardens) and Students, along with secure authentication and database management.

Features

Security & Authentication
- **Password Hashing:** Uses PHP `password_hash()` (bcrypt) and `password_verify()` for secure logins.
- **Session Tracking:** Server-side PHP `$_SESSION` management with `HttpOnly` and `SameSite=Lax` cookies.
- **Session Fixation Protection:** Uses `session_regenerate_id()` upon successful login.
- **Role-Based Access Control (RBAC):** Separate secure routes for Admin and Student.
- **Ownership Checks:** Students can only view, edit, or delete their *own* complaints and visitors.

Admin Panel
- **Dashboard:** Real-time stats on occupancy, complaints, and fee collections.
- **Student Management:** Add, edit, view, and delete student records.
- **Room Management:** Manage room inventory, capacity, and status.
- **Room Allocation:** Assign students to specific rooms and beds.
- **Complaints & Maintenance:** Track and resolve student issues.
- **Visitor Log:** Monitor visitor entries and check-outs.
- **Payments:** Record fee transactions and view history.

Student Panel
- **Dashboard:** Snapshot of room details, fee status, and recent notices.
- **Profile Management:** Update personal contact details.
- **My Room:** View room number, bed, and roommates.
- **Complaints:** Raise new maintenance/issue tickets.
- **Visitors:** Pre-register visitors.
- **Payments:** View fee summary and transaction history.
- **Notifications:** View announcements and mark them as read.

---

Tech Stack
- **Backend:** PHP 8.x
- **Database:** MySQL (via XAMPP)
- **Frontend:** HTML5, CSS3, Vanilla JavaScript
- **Database Connection:** PDO (PHP Data Objects) with prepared statements to prevent SQL injection.

---

How to Run This Project Locally

1. **Install XAMPP:** Download and install XAMPP from [apachefriends.org](https://www.apachefriends.org/).
2. **Start Services:** Open XAMPP Control Panel and start **Apache** and **MySQL**.
3. **Clone/Move Project:** Place this project folder inside the `C:\xampp\htdocs\` directory. Ensure the folder is named `hostel-management`.
4. **Set up the Database:**
   - Open your browser and go to `http://localhost/phpmyadmin`
   - Create a new database named `hostel_management` (collation: `utf8mb4_general_ci`).
   - Import the `db.sql` file provided in the project, OR let the system auto-create it.
   - *Important:* Open `config/db.php` and check your database credentials (default XAMPP is user: `root`, password: blank).
5. **Run the App:** Open `http://localhost/hostel-management/` in your browser.

---

Default Demo Credentials

*(Note: Passwords are automatically hashed in the database for security)*

**Admin Login:**
- Email: `admin@hostel.com`
- Password: `admin123`

**Student Login:**
- Email: `riya@hostel.com`
- Password: `student123`

---Important Notes for Evaluators

1. **Database Schema Match:** The PHP backend is strictly written for the schema provided in the original documentation. Ensure tables are named `admins`, `students`, `rooms`, etc. (lowercase), as the code uses lowercase table names.
2. **One-Time Migration:** If you are using an older version of the database with plain-text passwords, you may need to run `migrate_passwords.php` once to hash the existing passwords. (This file is excluded from the repository for security).

---
*Created as a College Project for Hostel Management.*
