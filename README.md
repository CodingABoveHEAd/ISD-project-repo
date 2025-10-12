# 🚑 Emergency Ambulance Hiring Portal

A comprehensive, full-stack web application designed to streamline the process of hiring and tracking emergency and non-emergency ambulance services.

This project was developed as a team course submission to demonstrate proficiency in PHP, MySQL database management, and robust web application structuring.

## ✨ Features

### Public User Interface
* **Quick Booking:** Users can quickly submit all necessary patient, relative, and location details using the primary form on `index.php`.
* **Unique Booking Number:** Upon submission, a unique 9-digit `BookingNumber` is generated and provided to the user for tracking.
* **Real-time Tracking:** Users can track the status of their request (`New`, `Assigned`, `On the way`, `Pickup`, etc.) by searching using their Booking Number, Patient Name, or Contact Number via `ambulance-tracking.php`.
* **Detailed Status History:** The `booking-details.php` page provides a full chronological log of all status updates, along with the assigned Driver Name and Contact Number (if assigned).

### Administrator Panel (`admin/`)
* **Asset Management:** CRUD operations (Add, Edit, Delete, Manage) for the ambulance fleet (registration number, driver details).
* **Request Workflow Management:** Dedicated pages to manage the request lifecycle:
    * `new-ambulance-request.php` (for initial assignment).
    * `ontheway-ambulance-request.php`, `pickup-ambulance-request.php`, `reached-ambulance-request.php` (for status updates).
* **Reporting:** Tools to generate reports, including `ambulance-request-report.php` and `bwdates-request-report-details.php`.
* **Configuration:** Ability to update contact information and "About Us" page content via `tblpage`.

## 🛠️ Technology Stack

| Component | Technology | Version / Notes |
| :--- | :--- | :--- |
| **Backend** | **PHP** | Procedural scripting language (Core logic) |
| **Database** | **MySQL** | `ccbd_ambulance` schema |
| **Database Connector** | **`mysqli`** | Used for database connections and queries |
| **Frontend** | **HTML5 / CSS3 / JavaScript** | Standard web technologies |
| **Framework** | **Bootstrap** | Used for responsive design and UI components |

## 🚀 Installation and Setup

### 1. Prerequisites

Ensure you have a local server environment installed (e.g., XAMPP, WAMP, MAMP) which includes:
* PHP (v5.6 or later recommended)
* MySQL/MariaDB

### 2. Database Setup

1.  Open your PHPMyAdmin interface (usually `http://localhost/phpmyadmin/`).
2.  Create a new database named **`ccbd_ambulance`**.
3.  Import the SQL file: **`ccbd_ambulance.sql`** into the newly created database.

### 3. Code Deployment

1.  Clone this repository or download the source code ZIP.
2.  Place the entire project folder (including the `admin`, `assets`, `database`, and `includes` folders) into your web server's root directory (e.g., `htdocs` for XAMPP).

### 4. Configure Database Connection

The connection details are configured in `includes/dbconnection.php`:
```php
<?php
$con=mysqli_connect("localhost", "root", "", "ccbd_ambulance");
if(mysqli_connect_errno()){
echo "Connection Fail".mysqli_connect_error();
}
// Note: If you are not using 'root' with an empty password, update these credentials.
?>