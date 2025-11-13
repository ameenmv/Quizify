# 🧠 Quizify — Interactive Quiz Platform

## 📋 Project Overview
**Quizify** is a full-stack interactive quiz platform that allows admins to create quizzes and users to attempt them with real-time scoring and a countdown timer.  
This project aims to demonstrate both **front-end interactivity (Vue + GSAP)** and **back-end CRUD logic (Laravel + REST API)** in a clean, scalable structure.

---

## 🧩 Roles
### 👨‍💼 Admin
- Create, edit, and delete quizzes.
- Add questions and multiple-choice answers.
- View statistics (participants count, average scores).

### 👤 User
- Register & login.
- Browse available quizzes.
- Attempt quizzes with a countdown timer.
- View results and scores after completion.

---

## ⚙️ Tech Stack

| Layer | Technology |
|--------|-------------|
| **Frontend** | Vue 3, Pinia, Tailwind CSS, GSAP, Axios |
| **Backend** | Laravel 11, MySQL, Laravel Sanctum (Auth) |
| **Tools** | Git, GitHub, Postman, VS Code |
| **Hosting** | Frontend: Netlify — Backend: Render / Railway |

---

## 🗂️ Folder Structure

### 🖥️ Frontend (Vue)
```
quizify-frontend/
├── src/
│   ├── assets/           # images, icons, etc.
│   ├── components/       # reusable components (buttons, modals, timer)
│   ├── layouts/          # layout components (admin, user, auth)
│   ├── pages/            # main views (Home, Quiz, Results, Dashboard)
│   ├── store/            # Pinia stores (auth, quiz, result)
│   ├── router/           # Vue Router routes
│   ├── services/         # Axios API handlers
│   ├── utils/            # helper functions (timer, score calc)
│   └── App.vue
│
└── package.json
```

### ⚙️ Backend (Laravel)
```
quizify-backend/
├── app/
│   ├── Http/
│   │   ├── Controllers/
│   │   │   ├── AuthController.php
│   │   │   ├── QuizController.php
│   │   │   ├── QuestionController.php
│   │   │   └── ResultController.php
│   │   └── Middleware/
│   ├── Models/
│   │   ├── User.php
│   │   ├── Quiz.php
│   │   ├── Question.php
│   │   ├── Answer.php
│   │   └── UserQuiz.php
│   └── ...
│
├── database/
│   ├── migrations/      # all DB tables
│   └── seeders/
│
├── routes/
│   ├── api.php          # all API endpoints
│
└── composer.json
```

---

## 🗄️ Database Design

### **users**
| Column | Type | Description |
|---------|------|-------------|
| id | int | Primary key |
| name | string | User name |
| email | string | Unique |
| password | string | Hashed password |
| role | enum('admin','user') | User role |
| created_at | timestamp | — |

### **quizzes**
| Column | Type | Description |
|---------|------|-------------|
| id | int | Primary key |
| title | string | Quiz title |
| description | text | Quiz info |
| duration | int | Duration in minutes |
| difficulty | enum('easy','medium','hard') | Level |
| created_by | foreignId(users) | Admin who created it |

### **questions**
| Column | Type | Description |
|---------|------|-------------|
| id | int | Primary key |
| quiz_id | foreignId(quizzes) | Quiz reference |
| question_text | text | The question |

### **answers**
| Column | Type | Description |
|---------|------|-------------|
| id | int | Primary key |
| question_id | foreignId(questions) | Question reference |
| answer_text | text | Answer text |
| is_correct | boolean | True if correct |

### **user_quizzes**
| Column | Type | Description |
|---------|------|-------------|
| id | int | Primary key |
| user_id | foreignId(users) | User reference |
| quiz_id | foreignId(quizzes) | Quiz reference |
| score | int | Result percentage |
| completed_at | timestamp | Submission time |

---

## 📡 API Endpoints

### **Auth**
| Method | Endpoint | Description |
|---------|-----------|-------------|
| POST | /api/register | Register new user |
| POST | /api/login | Login user |
| GET | /api/me | Get logged-in user |

### **Admin**
| Method | Endpoint | Description |
|---------|-----------|-------------|
| GET | /api/quizzes | Get all quizzes |
| POST | /api/quizzes | Create quiz |
| POST | /api/quizzes/{id}/questions | Add questions to quiz |
| DELETE | /api/quizzes/{id} | Delete quiz |

### **User**
| Method | Endpoint | Description |
|---------|-----------|-------------|
| GET | /api/quizzes | Get all quizzes |
| GET | /api/quizzes/{id} | Get quiz details (questions & answers) |
| POST | /api/quizzes/{id}/submit | Submit answers and get score |
| GET | /api/results | Get user’s past results |

---

## 🧠 Core Logic

- **Timer System:**  
  Countdown using `setInterval()` + visual circular progress.

- **Score Calculation:**  
  Compare selected answers with correct ones, calculate accuracy, and send score to backend.

- **Animations:**  
  Smooth transitions between questions using GSAP (`fade`, `slide`, `flip`).

- **Protected Routes:**  
  Using Laravel Sanctum for API auth and frontend route guards in Vue.

---

## 🪄 UI Pages (Frontend)

1. `/login` — login/register screen  
2. `/` — homepage (list of quizzes)  
3. `/quiz/:id` — take quiz  
4. `/result/:id` — result page  
5. `/admin` — dashboard for managing quizzes/questions  

---

## 🧰 Setup Guide

### Backend
```bash
cd quizify-backend
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate --seed
php artisan serve
```

### Frontend
```bash
cd quizify-frontend
npm install
npm run dev
```

---

## 🚀 Future Enhancements
- Add leaderboard (top scorers)
- Add quiz categories & filters
- Allow users to create custom quizzes
- Show per-question explanations after submission

---

## WorkFlow
https://www.sketchflow.ai/workFlow?project_id=39196&design_id=39842

---

## 👨‍💻 Author
**Ameen Mohamed**  
Front-End Developer (Vue.js | Tailwind | Laravel)  
📧 [ameeenmv@gmail.com](mailto:ameeenmv@gmail.com)  
🌐 [Portfolio](https://ameeenmv.netlify.app/)  
🐙 [GitHub](https://github.com/ameenmv)
