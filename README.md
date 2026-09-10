# flowtrack-wellness-app 🌸

A full-stack menstrual cycle planner and wellness tracker built with React, Express, and MySQL — featuring live cycle predictions, symptom insights, and phase-based wellness guidance.

## 👤 Author

Built by Hilina Ayalew as the final individual capstone project for the **WabiSkills Full-Stack Development Bootcamp**.

---
FlowTrack helps users log their cycle, understand their current phase, and receive personalized wellness guidance — turning daily tracking into visible, useful patterns over time rather than guesswork.

---

## 🎯 The Problem

Most people who menstruate don't track their cycle consistently until something feels off — by then, there's no baseline to compare against. FlowTrack is built around making daily tracking effortless, so patterns (cycle length changes, recurring symptoms, mood trends) become visible over time.

---

## ✨ Features

- **Secure Authentication** — JWT-based auth with bcrypt password hashing
- **Smart Dashboard** — live cycle phase indicator, countdown to next period, fertile window prediction, cycle length trend chart
- **Interactive Calendar** — color-coded month view (period / fertile / predicted days), click-to-log entries
- **Daily Logging** — track flow, mood, symptoms, and notes, with a recent-entries history view
- **Insights & Analytics** — cycle length trend chart, server-side aggregated symptom frequency chart, summary stats
- **Personalized Wellness Tips** — phase-based recommendations across nutrition, exercise, hydration, self-care, and stress management
- **Dark / Light Mode** — full theme system using CSS custom properties
- **Fully Responsive** — mobile, tablet, and desktop layouts

---

## 🛠️ Tech Stack

**Frontend**
- React.js (Vite)
- React Router DOM
- Axios
- Bootstrap + custom CSS (CSS variables for theming)
- Recharts (data visualization)
- react-calendar
- React Context API (auth state + theme state)

**Backend**
- Node.js + Express.js
- JWT (jsonwebtoken) — authentication
- bcrypt — password hashing
- mysql2 — database driver (Promise-based)
- dotenv, cors

**Database**
- MySQL (MySQL Workbench)

---

## 🗄️ Database Schema

**users**
| Column | Type |
|---|---|
| id | INT, PK, AUTO_INCREMENT |
| name | VARCHAR(100) |
| email | VARCHAR(100), UNIQUE |
| password | VARCHAR(255) (hashed) |
| created_at | TIMESTAMP |

**cycles**
| Column | Type |
|---|---|
| id | INT, PK, AUTO_INCREMENT |
| user_id | INT, FK → users(id) |
| last_period_date | DATE |
| cycle_length | INT, DEFAULT 28 |
| period_length | INT, DEFAULT 5 |

**logs**
| Column | Type |
|---|---|
| id | INT, PK, AUTO_INCREMENT |
| user_id | INT, FK → users(id) |
| log_date | DATE |
| flow | ENUM('none','light','medium','heavy') |
| mood | VARCHAR(50) |
| symptoms | TEXT |
| notes | TEXT |

All foreign keys use `ON DELETE CASCADE`.

---

## 📁 Project Structure
