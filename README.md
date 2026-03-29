<div align="center">
  <h1 align="center">LibSmart - Library Management System</h1>
  <p align="center">
    A comprehensive library management web application built with Core PHP (MVC architecture).
    <br />
    <a href="#features"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="#installation">Installation</a>
    ·
    <a href="#features">Features</a>
    ·
    <a href="#project-structure">Architecture</a>
  </p>
</div>

## 📖 About The Project

LibSmart is a web-based **Library Management System** developed using **Core PHP** and the **MVC (Model-View-Controller)** architecture. It is designed to streamline library operations for librarians, staff, and readers, providing an intuitive interface for book management, borrowing and returning workflows, as well as an AI-powered chatbot consultant using the Gemini API.

## ✨ Features

- **Role-Based Access Control**: Different access privileges for Readers, Staff, and Managers/Librarians.
- **Book & Category Management**: Seamlessly add, update, delete, and categorize books.
- **Borrowing & Returning System**: Track borrowed books, manage return dates, and monitor stock quantities.
- **Fine Management**: Issue and manage penalty tickets for late returns or damaged books.
- **Advanced Search**: Quickly search the library catalog for books by title, author, or category.
- **Reports & Statistics**: Generate comprehensive reports on library activities and book statuses.
- **AI Chatbot**: Integrated with the Google Gemini API to provide an intelligent virtual assistant for readers.
- **Email Notifications**: Built-in support for sending emails (e.g., account recovery, notifications) using PHPMailer.

## 🛠 Built With

- **Backend**: Core PHP (Object-Oriented & MVC)
- **Database**: MySQL
- **Frontend**: HTML5, CSS3, JavaScript
- **API Integration**: Google Gemini API
- **Packages**: PHPMailer (via Composer)
- **Server Environment**: Laragon / XAMPP / WAMP

## 🚀 Getting Started

Follow these simple instructions to set up the project locally on your machine.

### Prerequisites

- PHP >= 8.0
- MySQL Server
- [Composer](https://getcomposer.org/) (for managing PHP dependencies)
- A local development server like [Laragon](https://laragon.org/) or [XAMPP](https://www.apachefriends.org/)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/NguyenDinhKhang1100604/LibSmart-website-quan-ly-thu-vien.git
   ```

2. **Move to the project directory**
   Move the cloned folder into your web server's document root (e.g., `C:\laragon\www\LibSmart` or `C:\xampp\htdocs\LibSmart`), then open your terminal inside the project directory:
   ```bash
   cd LibSmart
   ```

3. **Install Dependencies**
   Run the following command to install required packages like PHPMailer:
   ```bash
   composer install
   ```

4. **Database Setup**
   You have two options to set up the database:
   - **Option A (Recommended)**: Import the provided `sql_LibSmart.sql` file into your MySQL database using phpMyAdmin or a similar database management tool.
   - **Option B**: Run the initialization script in your browser to automatically create the database (`libsmart`) and default tables:
     ```text
     http://localhost/LibSmart/init_db.php
     ```

5. **Configure Database Connection**
   Open `config/db.php` and verify the database credentials match your local MySQL setup:
   ```php
   $servername = "localhost";
   $username = "root";
   $password = ""; // Your MySQL password
   $dbname = "libsmart";
   ```

6. **Configure Gemini API Key**
   To enable the AI chatbot functionality, open `config/gemini.php` and add your Google Gemini API key:
   ```php
   return [
       'api_key' => 'YOUR_GEMINI_API_KEY_HERE',
       'endpoint' => 'https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent',
   ];
   ```

## 🔑 Default Accounts

If you used the `init_db.php` script, the following default accounts are created:

- **Manager Account**
  - Username: `admin`
  - Password: `123456`
- **Reader Account**
  - Username: `reader`
  - Password: `123456`

## 📂 Project Structure

```text
LibSmart/
├── config/         # App configuration (Database, Gemini API)
├── controllers/    # Logic to handle incoming requests & responses
├── helpers/        # Global helper utilities
├── models/         # Database interaction layers
├── public/         # Static assets (CSS, JS, Images)
├── vendor/         # Composer dependencies
├── views/          # UI templates and layouts
├── composer.json   # Package dependency declarations
├── init_db.php     # Quick database initialization file
├── README.md       # Project documentation
└── sql_LibSmart.sql# Full database schema & seed data dump
```

## 📄 License

Distributed under the MIT License.
