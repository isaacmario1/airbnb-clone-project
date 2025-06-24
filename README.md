# AirBnB Clone Project

## Overview
This project is a clone of the AirBnB website created for educational purposes. It aims to replicate core functionalities of the original platform including property listings, user authentication, booking system, and more.

The goal is to gain practical experience in full-stack web development using modern tools and best practices.

## Project Goals
- Understand and implement RESTful APIs.
- Build dynamic front-end interfaces.
- Practice object-oriented programming and database management.
- Collaborate effectively using Git and GitHub.

## Tech Stack
- **Frontend:** HTML, CSS, JavaScript, React (optional)
- **Backend:** Python, Flask (or Django)
- **Database:** MySQL / PostgreSQL / SQLite
- **Version Control:** Git & GitHub
- **Deployment:** Render / Heroku / Docker (optional)

## Team Roles

Below are the key roles involved in the AirBnB Clone project and their responsibilities:

### 👨‍💻 Backend Developer
Responsible for developing and maintaining the server-side logic of the application. This includes building APIs, implementing business logic, managing integrations, and ensuring data flows securely between the server and client.

### 🎨 Frontend Developer
Handles the user interface and user experience. Works on building dynamic, responsive web pages using HTML, CSS, JavaScript, and frameworks like React (optional). Ensures seamless interaction between the user and the backend systems.

### 🧠 Database Administrator (DBA)
Designs and manages the database schema and queries. Responsible for ensuring data integrity, performance optimization, backup strategies, and security of user data.

### 🧪 Quality Assurance (QA) Tester
Ensures the application meets quality standards through testing. Performs manual and automated tests to find bugs, verify functionality, and validate performance before deployment.

### 🛠 DevOps Engineer
Handles deployment, CI/CD pipelines, and server management. Ensures smooth integration, scaling, and availability of the application. May use tools like Docker, GitHub Actions, or Render for deployment.

### 📋 Project Manager
Oversees project planning, coordination, and communication among team members. Sets milestones, tracks progress, and ensures the team meets deadlines and delivers the required functionality.

### 🛡️ Security Specialist *(Optional but important)*
Ensures the application is secure from threats. Implements authentication, authorization, encryption, and secure coding practices to protect user data and privacy.

---

These roles may overlap or be shared depending on the team size. For solo or small-team projects, individuals may take on multiple responsibilities.


## Technology Stack

This project leverages a modern full-stack development toolkit to replicate the functionality of the AirBnB platform. Below is a list of the core technologies used and their purposes:

### 🔧 Django
A high-level Python web framework used for rapid development of secure and scalable web applications. Django handles the backend logic, routing, RESTful API creation, user authentication, and admin interface.

### 🐘 PostgreSQL
An advanced, open-source relational database system used to store structured data such as user accounts, property listings, and booking information. It integrates well with Django and supports complex queries and transactions.

### 🌐 HTML, CSS, JavaScript
Used to build the static structure (HTML), styling (CSS), and interactive behavior (JavaScript) of the frontend interface.

### ⚛️ React (Optional for Frontend)
A JavaScript library for building user interfaces. React helps create dynamic, reusable components and offers a better user experience through single-page application (SPA) architecture.

### 🚀 GraphQL (Optional)
A query language for APIs that allows clients to request only the data they need. Can be used as an alternative to REST for more efficient data fetching between frontend and backend.

### 🐳 Docker (Optional)
Used to containerize the application and ensure consistent development, testing, and deployment environments across all machines.

### 🔄 Git & GitHub
Version control system (Git) and code hosting platform (GitHub) are used for collaborative development, issue tracking, and maintaining the project history.

### ✅ GitHub Actions (CI/CD)
Automates workflows such as testing, deployment, and linting whenever changes are pushed to the repository.

---

These technologies work together to deliver a robust, scalable, and maintainable AirBnB clone platform.


## Database Design

The database structure for the AirBnB Clone project is designed to support user activity, property listings, bookings, reviews, and payments. Below are the key entities and their relationships:

### 🧍 Users
Represents users of the platform, including both hosts and guests.

**Key Fields:**
- `id`: Unique identifier (Primary Key)
- `username`: User's display name
- `email`: Unique email address
- `password_hash`: Hashed password for security
- `is_host`: Boolean flag to distinguish hosts from guests

**Relationships:**
- A user can list multiple properties.
- A user can make multiple bookings.
- A user can leave multiple reviews.

---

### 🏠 Properties
Represents accommodations listed by hosts.

**Key Fields:**
- `id`: Unique property ID
- `owner_id`: Foreign key to Users table
- `title`: Name or title of the property
- `description`: Detailed description
- `location`: Address or coordinates
- `price_per_night`: Cost for one night

**Relationships:**
- Each property is owned by one user (host).
- A property can have multiple bookings.
- A property can receive multiple reviews.

---

### 📅 Bookings
Tracks reservations made by guests.

**Key Fields:**
- `id`: Unique booking ID
- `user_id`: Foreign key to Users table (the guest)
- `property_id`: Foreign key to Properties table
- `start_date`: Check-in date
- `end_date`: Check-out date
- `total_price`: Final calculated price

**Relationships:**
- A booking is made by one user for one property.

---

### ⭐ Reviews
Contains feedback from users about properties.

**Key Fields:**
- `id`: Unique review ID
- `user_id`: Foreign key to Users table
- `property_id`: Foreign key to Properties table
- `rating`: Integer score (e.g., 1–5)
- `comment`: Text review

**Relationships:**
- A user can write a review for a property.
- A property can have many reviews.

---

### 💳 Payments
Tracks payment transactions for bookings.

**Key Fields:**
- `id`: Unique payment ID
- `booking_id`: Foreign key to Bookings table
- `amount`: Payment amount
- `payment_method`: e.g., credit card, PayPal
- `status`: Paid, pending, failed
- `timestamp`: Time of payment

**Relationships:**
- Each payment is linked to one booking.

---

### 🔗 Entity Relationships Summary

- **User ↔ Property**: One-to-many (One user can own many properties).
- **User ↔ Booking**: One-to-many (One user can make many bookings).
- **Property ↔ Booking**: One-to-many (One property can be booked many times).
- **Property ↔ Review**: One-to-many (One property can have many reviews).
- **User ↔ Review**: One-to-many (One user can write many reviews).
- **Booking ↔ Payment**: One-to-one (Each booking has one payment record).

This relational database structure ensures data consistency and supports the core functionality of the AirBnB Clone platform.

## Feature Breakdown

The AirBnB Clone project includes several core features that replicate the functionality of the original AirBnB platform. Each feature plays a vital role in delivering a complete and user-friendly experience.

### 👥 User Management
Allows users to register, log in, and manage their profiles securely. Includes role-based access for guests and hosts, ensuring that each user has access to relevant tools and data.

### 🏠 Property Management
Hosts can list their properties with detailed information, photos, pricing, and availability. This feature enables hosts to manage listings and attract bookings from potential guests.

### 📅 Booking System
Enables guests to search for available properties, choose booking dates, and reserve accommodations. It ensures that overlapping bookings are avoided and confirmations are sent upon successful booking.

### 💳 Payment Integration
Supports secure payment processing for reservations using common methods like credit/debit cards or third-party gateways. Payments are linked to bookings and tracked for both users and hosts.

### ⭐ Reviews and Ratings
After completing a stay, guests can leave reviews and ratings for properties. This helps future guests make informed decisions and encourages hosts to maintain high standards.

### 🔍 Search and Filter
Provides a robust search feature that allows users to filter listings based on location, price, amenities, and availability. Improves user experience by making it easy to find the right property quickly.

### 🖼️ Property Image Gallery
Each property listing includes a photo gallery to showcase accommodations. High-quality visuals improve credibility and attract more bookings.

### 🔐 Authentication & Authorization
Uses secure authentication mechanisms (e.g., hashed passwords, JWT tokens) to protect user data. Ensures that only authorized users can access sensitive features like property management and payments.

### 🛠 Admin Panel (Optional)
An optional admin dashboard to monitor users, listings, and bookings. Useful for platform administrators to manage and moderate activity.

---

Each of these features helps recreate a functional, full-stack rental platform and provides learning opportunities across backend, frontend, and database systems.

## Author
Mwangale Isaac Maliro – [isaacmario1](https://github.com/isaacmario1)

## License
This project is open-source and available under the [MIT License](LICENSE).
