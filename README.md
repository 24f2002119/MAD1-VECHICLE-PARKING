 🚗 Vehicle Parking App - V1

A multi-user vehicle parking management system built using **Flask**, **Jinja2**, **Bootstrap**, and **SQLite** (with SQLAlchemy ORM). This project is developed as part of the **Modern Application Development I (MAD1)** course.

---

## 📌 Project Overview

This web-based application allows:
- **Admins** to manage parking lots and monitor spot status.
- **Users** to register/login, reserve parking spots, and track their parking history and cost.

All parking spots are for **4-wheelers only** and parking spot allocation is handled automatically.

---

## 🧰 Technologies Used

| Layer        | Framework / Library      |
|--------------|---------------------------|
| Backend      | Flask, Flask-SQLAlchemy   |
| Frontend     | Jinja2, HTML, CSS, Bootstrap |
| Database     | SQLite (created via code, not manually) |

---

## 🔐 Roles and Features

### 👨‍💼 Admin (Superuser)
- No registration/login needed (hardcoded in DB)
- Add/Edit/Delete Parking Lots
- Auto-generate parking spots per lot capacity
- View parking lot status (Available/Occupied)
- View all registered users
- View all reservations and parked vehicles

### 👤 User
- Register/Login
- Choose a parking lot (auto-spot allocation)
- Occupy/Release parking spot
- View personal parking history and cost summary

---

## 🗃️ Database Models (ER Overview)

1. **User**
   - `id`, `name`, `email`, `password`, `pincode`, `created_at`

2. **ParkingLot**
   - `id`, `location_name`, `address`, `pincode`, `price`, `max_spots`, `created_at`

3. **ParkingSpot**
   - `id`, `lot_id (FK)`, `status`

4. **Reservation**
   - `id`, `spot_id (FK)`, `user_id (FK)`, `in_time`, `out_time`, `total_cost`, `status`

> Admin user is implicitly created in the DB during initialization.

---

## 📁 Folder Structure

```

project/
│
├── app.py                 # Main Flask application
├── models.py              # SQLAlchemy models
├── routes.py              # Application routes
├── extensions.py          # DB & other Flask extensions
├── requirements.txt       # Dependencies
├── README.md              # Project info
├── instance/              # SQLite DB lives here
├── static/                # CSS
├── templates/             # HTML (Jinja2) templates
├── .venv/                 # Virtual environment (excluded from Git)
└── .gitignore

````

---

## 🧪 Getting Started (Local Setup)

```bash
# Clone repo & enter directory
git clone <your-private-repo-url>
cd project

# Create & Activate virtualenv
python3 -m venv .venv
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run the app
python app.py
````

Database and admin user are created automatically on first run.


## ✅ Milestone Tracker

* ✅ Milestone 0: GitHub Repo Setup
* ✅ Milestone 1: Database Models & Schema
* ✅ Milestone 2: Authentication & RBAC
* ✅ Milestone 3: Admin Dashboard + Lot/Spot Management
* ✅ Milestone 4: User Dashboard + Reservation System
* ✅ Milestone 5: Parking History Summary
* ✅ Milestone 6: Cost Calculation Module
