# pets_victoria_paid-project  

A simple, extensible web application for managing and showcasing pets. Built with PHP and a lightweight front‑end, it provides CRUD operations, user authentication, and a searchable gallery.

---  

## Overview  

`pets_victoria_paid-project` is a PHP‑based platform that allows administrators and registered users to:

* Add, edit, view, and delete pet records.  
* Browse a responsive gallery of pet photos.  
* Search pets by name, breed, or owner.  
* Manage user accounts (registration, login, logout).  

The project is organized with a clear separation of concerns: database scripts, core PHP pages, reusable includes, and styling assets.

---  

## Features  

| ✅ | Feature |
|---|---|
| ✔️ | **Full CRUD** – `add.php`, `edit.php`, `delete.php`, `details.php`. |
| ✔️ | **User Management** – registration, login, logout, profile (`register.php`, `login.php`, `logout.php`, `user.php`). |
| ✔️ | **Search & Filter** – global search (`search.php`, `navsearch.php`) and gallery filtering. |
| ✔️ | **Responsive UI** – CSS styling (`assets/css/style.css`) and reusable layout components (`header.inc`, `footer.inc`, `nav.inc`). |
| ✔️ | **Database Schema** – ready‑to‑import MySQL dump (`Database/pets.sql`). |
| ✔️ | **Modular Includes** – database connection (`db_connect.inc`) and navigation. |
| ✔️ | **Secure Sessions** – basic session handling for authentication. |

---  

## Tech Stack  

| Layer | Technology |
|-------|------------|
| Backend | PHP 7.4+ |
| Database | MySQL / MariaDB |
| Front‑end | HTML5, CSS3 (custom stylesheet) |
| Server | Apache / Nginx (with PHP-FPM) |
| Version Control | Git (GitHub) |

---  

## Installation  

1. **Clone the repository**  

   ```bash
   git clone https://github.com/yourusername/pets_victoria_paid-project.git
   cd pets_victoria_paid-project
   ```

2. **Create a MySQL database**  

   ```sql
   CREATE DATABASE pets_victoria;
   ```

3. **Import the schema**  

   ```bash
   mysql -u your_user -p pets_victoria < Database/pets.sql
   ```

4. **Configure the database connection**  

   Edit `include/db_connect.inc` and replace the placeholder values with your own credentials:

   ```php
   $host = 'localhost';
   $db   = 'pets_victoria';
   $user = 'YOUR_DB_USERNAME';
   $pass = 'YOUR_DB_PASSWORD';
   $charset = 'utf8mb4';
   ```

5. **Set up a web server**  

   - Place the project folder inside your web root (e.g., `/var/www/html/pets_victoria`).  
   - Ensure the server points to `index.php` as the default document.  
   - Enable PHP processing and restart the server.

6. **(Optional) Configure API keys**  

   If you integrate third‑party services (e.g., Google Maps for pet locations), store the keys in a separate config file and reference them as `YOUR_OWN_API_KEY`.

---  

## Usage  

| Action | URL | Description |
|--------|-----|-------------|
| Home / Gallery | `http://yourdomain.com/` | Shows the pet gallery (`gallery.php`). |
| View Pet Details | `http://yourdomain.com/details.php?id=XX` | Detailed view of a single pet. |
| Add New Pet | `http://yourdomain.com/add.php` | Form for creating a new pet record (admin only). |
| Edit Pet | `http://yourdomain.com