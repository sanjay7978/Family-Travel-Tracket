# 🌍 Family Travel Tracker

A full-stack web application that allows family members to track and manage the countries they have visited. Users can switch between profiles, add new countries, and maintain their own travel history.

## 📸 Preview

Track visited countries for different family members and visualize travel progress in a simple and interactive interface.

---

## 🚀 Features

- 👨‍👩‍👧‍👦 Multiple user profiles
- 🌎 Add countries visited by each family member
- 🗄️ PostgreSQL database integration
- 🔄 Dynamic server-side rendering using EJS
- 🎨 Personalized user colors
- ⚡ Fast and lightweight Express.js backend

---

## 🛠️ Tech Stack

### Frontend
- HTML
- CSS
- EJS

### Backend
- Node.js
- Express.js

### Database
- PostgreSQL

### Packages
- pg
- express
- body-parser
- ejs

---

## 📂 Project Structure

```text
Family Travel Tracker
│
├── public/
│   ├── styles/
│   └── images/
│
├── views/
│   ├── index.ejs
│   └── new.ejs
│
├── index.js
├── package.json
└── queries.sql
```

---

## 🗃️ Database Schema

### Users Table

```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name TEXT UNIQUE NOT NULL,
    color TEXT NOT NULL
);
```

### Countries Table

```sql
CREATE TABLE countries (
    id SERIAL PRIMARY KEY,
    country_code CHAR(2) UNIQUE NOT NULL,
    country_name TEXT NOT NULL
);
```

### Visited Countries Table

```sql
CREATE TABLE visited_countries (
    id SERIAL PRIMARY KEY,
    country_code CHAR(2) NOT NULL,
    user_id INTEGER REFERENCES users(id)
);
```

---

## ⚙️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/family-travel-tracker.git
cd family-travel-tracker
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Create PostgreSQL Database

```sql
CREATE DATABASE world;
```

Run the SQL queries to create the required tables.

### 4. Configure Database Connection

Update your PostgreSQL credentials in:

```javascript
const db = new pg.Client({
  user: "postgres",
  host: "localhost",
  database: "world",
  password: "your_password",
  port: 5432,
});
```

### 5. Start the Application

```bash
nodemon index.js
```

or

```bash
node index.js
```

---

## 🎯 How It Works

1. Select a family member.
2. Enter a country name.
3. The application searches for the corresponding country code.
4. The country is stored in the database.
5. The travel map updates automatically.
6. Add new users and maintain separate travel histories.

---

## 📚 Learning Outcomes

This project helped me learn:

- PostgreSQL CRUD Operations
- SQL Joins
- One-to-Many Relationships
- Express.js Routing
- EJS Templating
- Backend Development with Node.js
- Database Integration using pg

---

## 🔮 Future Improvements

- User Authentication
- Interactive World Map
- Travel Statistics Dashboard
- Country Notes & Photos
- Delete/Edit Visited Countries
- Responsive Mobile Design

---

## 👨‍💻 Author

**Sanjay Repaka**

B.Tech CSE Student | Full Stack Development Enthusiast

---

## ⭐ Support

If you found this project useful, consider giving it a star ⭐ on GitHub.
