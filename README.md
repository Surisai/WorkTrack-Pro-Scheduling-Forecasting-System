# WorkTrack Pro – Scheduling & Forecasting System

## 📌 Overview
**WorkTrack Pro** is a centralized platform for managing employee schedules, detecting shift conflicts, and forecasting seasonal staffing needs.  
It’s designed for managers and employees to have **real-time, transparent access** to scheduling data, while automating key processes like conflict checking and staffing predictions.

---

## 🎯 Goals
- Eliminate shift conflicts and scheduling errors.
- Reduce manual spreadsheet work with a **centralized SQL database**.
- Accurately predict staffing needs based on **seasonal trends**.
- Give employees visibility and control over their schedules.
- Support both **manager** and **employee** roles with role-based access control (RBAC).

---

## 🛠 Technology Stack

| Layer          | Technology |
|----------------|------------|
| **Frontend**   | HTML, CSS, JavaScript, Bootstrap, FullCalendar.js |
| **Backend**    | Python (FastAPI) for API, C++ (core scheduling logic) |
| **Forecasting**| Python (Pandas, NumPy, scikit-learn) |
| **Database**   | PostgreSQL or MySQL |
| **Auth**       | JWT-based authentication, RBAC |
| **Reporting**  | PDF export (WeasyPrint or ReportLab) |

---

## 🔑 Core Features

### 1. Employee Management
- Add/edit employee profiles (name, role, availability, skills).
- Store data in an SQL database.
- Manager vs. employee access control.

### 2. Shift Scheduling
- Calendar interface for creating and assigning shifts.
- C++ backend checks for:
  - Overlapping shifts
  - Employee availability
  - Role/skill mismatches
- Automatic alerts for conflicts.

### 3. Labor Forecasting
- Historical staffing data analysis.
- Seasonal demand prediction using machine learning.
- Suggestions for optimal number of employees per shift.

### 4. Web Dashboard
- **Manager View:** Create/modify schedules, view forecasts, approve requests.
- **Employee View:** View assigned shifts, request changes.
- Real-time sync with SQL database.

### 5. Reports & Analytics
- Export monthly schedule as PDF.
- View charts for:
  - Overtime hours
  - Forecast accuracy
  - Staffing trends

---
## Class diagram & Example of Sequan diagram
![Alt text](images/se.png)

---
![Alt text](images/class.png)


## 🔄 Workflow

```mermaid
flowchart LR
    A[Frontend UI] -->|API Calls| B[FastAPI Backend]
    B --> C[PostgreSQL Database]
    B --> D[C++ Scheduling Core]
    B --> E[Python Forecasting Module]
    D --> B
    E --> C
    C --> B
    B --> A

