# 🏛️ Grievance Management System (GMS)

> **A centralized, secure, and role-driven digital platform for managing public grievances at the district administration level.**

---

## 📌 Table of Contents

* [Overview](#-overview)
* [Problem Statement & Solution](#-problem-statement--solution)
* [User Roles & Privilege Hierarchy](#-user-roles--privilege-hierarchy)
* [System Architecture](#-system-architecture)
* [Database Design](#-database-design)
* [Technology Stack](#-technology-stack)
* [Detailed Workflow](#-detailed-workflow)
* [Security Mechanisms](#-security-mechanisms)
* [Key Features](#-key-features)
* [Installation & Setup](#-installation--setup)
* [Environment & Configuration](#-environment--configuration)
* [Warnings & Security Notes](#-warnings--security-notes)
* [Future Enhancements](#-future-enhancements)
* [Conclusion](#-conclusion)

---

## 🔹 Overview

The **Grievance Management System (GMS)** is a web-based administrative platform designed to digitally manage public grievances submitted to district administrations.

The system ensures that every grievance is:

* 📌 **Traceable**
* ⏱️ **Time-bound**
* 📋 **Audit-ready**

By enforcing clearly defined administrative roles and workflows, GMS improves transparency, accountability, and resolution efficiency.

---

## ❌ Problem Statement & Solution

### Problems Addressed

* Fragmented grievance submissions across multiple channels
* Manual tracking leading to delays in resolution
* Lack of accountability and administrative visibility
* No structured deadline enforcement
* Poor auditability of grievance handling

### System Solution

* Centralized grievance intake and tracking
* Role-Based Access Control (RBAC)
* Priority-based automatic deadline calculation
* Enforced accountability through system controls
* Complete audit trail for administrative review

---

## 👥 User Roles & Privilege Hierarchy

The system follows a strict **Role-Based Access Control (RBAC)** model.

### 🔑 User Roles

* System Administrator
* District Collector
* District Officer
* Head of Department (HOD)
* Department Officers
* Public Users
* Petition Entry Users

---

## 🛂 Privilege Details

| Role                         | Privileges                                                                  |
| ---------------------------- | --------------------------------------------------------------------------- |
| **System Administrator**     | Full system access, configuration, and maintenance                          |
| **District Collector**       | District-wide control, priority override, monitoring, administrative orders |
| **District Officer**         | District-level oversight (excluding sensitive operations)                   |
| **Head of Department (HOD)** | Department control, officer assignment, performance monitoring              |
| **Department Officers**      | Grievance execution, updates, inter-department requests                     |
| **Public Users**             | Grievance submission, document upload, status tracking                      |
| **Petition Entry Users**     | Digitization and entry of physical petitions                                |

🔐 *Sensitive operations require OTP and password verification.*

---

## 🏗️ System Architecture

* **Frontend** handles user interaction and dashboards
* **Backend (Django MVT)** manages business logic and workflows
* **Database (MySQL)** ensures normalized, consistent data storage
* **External APIs** enable multi-channel grievance intake

---

## 🗄️ Database Design

The system uses a **normalized relational database** implemented with **MySQL**.

### 📦 Core Tables

* `User`
* `PublicUserProfile`
* `District`
* `Department`
* `CollectorProfile`
* `DistrictOfficerProfile`
* `OfficerProfile`
* `IDTrackers`
* `Grievance`

### 🔄 Workflow Tables

* `GrievanceAssignment`
* `GrievanceFlow`
* `FlowStage`
* `GrievanceStatusLog`
* `GrievanceTransfer`

⚡ Indexes are applied on **status**, **priority**, and **due dates** for optimized performance.

---

## 🛠️ Technology Stack

### 💻 Frontend

* HTML
* CSS
* JavaScript

### ⚙️ Backend

* Django (Python) — **MVT Architecture**

### 🗃️ Database

* MySQL

### 🔌 Integrations

* Facebook Graph API
* WhatsApp API

---

## 🔁 Detailed Workflow

### 📝 1. Grievance Registration

* Submission via Web Portal, WhatsApp, Facebook, or Office Entry
* Unique grievance ID auto-generated
* Automatic district and department mapping

### 🏷️ 2. Classification & Priority

* Automatic priority assignment
* Due date calculated based on priority
* Priority modification allowed for District Collector

### 🏢 3. Department Assignment

* HOD assigns grievance to department officers
* Assignment logged with timestamps

### 👨‍💼 4. Officer Action & Updates

* Officers update grievance status periodically
* Updates visible to:

  * Higher authorities
  * Concerned departments
  * Public users

### 🔀 5. Inter-Department Transfer

* Officer initiates transfer request
* HOD approval required
* Complete transfer history maintained

### ⏰ 6. Deadline Enforcement

* Automated reminders before due date
* Mandatory justification for overdue grievances

### ✅ 7. Resolution & Closure

* Grievances marked as **Resolved** or **Rejected**
* Full lifecycle retained for audit purposes

---

## 🔐 Security Mechanisms

* Secure authentication and session management
* Role-based access enforcement
* OTP-based authorization for sensitive actions
* Dual authorization during Collector–District Officer handover
* Audit logging for all critical operations

---

## ⭐ Key Features

* Multi-channel grievance intake
* Role-specific dashboards
* Priority-based deadline management
* SMS and email acknowledgements
* Grievance tracking using unique ID
* Filtered and exportable reports (PDF / Excel)
* Administrative order management

---

## 💻 Installation & Setup

```bash
# Clone the repository
git clone https://github.com/jeevanjj004/Grivevance_MA.git

# Navigate to project directory
cd Grivevance_MA

# Create virtual environment
python -m venv venv

# Activate virtual environment
# Windows
venv\Scripts\activate

# Linux / macOS
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Database migrations
python manage.py makemigrations
python manage.py migrate

# Run development server
python manage.py runserver
```

🔗 Access the application at:

```
http://127.0.0.1:8000/
```

---

## 🌱 Environment & Configuration

Create a `.env` file in the project root:

```
SECRET_KEY=your_django_secret_key
DEBUG=True
DB_NAME=your_database
DB_USER=your_user
DB_PASSWORD=your_password
DB_HOST=localhost
DB_PORT=3306
FACEBOOK_API_KEY=xxxx
WHATSAPP_API_KEY=xxxx
```

---

## ⚠️ Warnings & Security Notes

### 🔑 API Keys & Tokens

* Never expose Facebook or WhatsApp API keys in the repository
* Store credentials securely using `.env` files or environment variables

### 🚨 Potential Errors

* Missing or invalid API credentials may cause runtime failures

### 🔒 Sensitive Data

* Never commit real user data or credentials

---

## 🚀 Future Enhancements

* Mobile application integration
* AI-based grievance categorization
* Advanced analytics & dashboards
* Multilingual support
* State-level aggregation and monitoring

---

## 🧾 Conclusion

The **Grievance Management System (GMS)** provides a structured, secure, and accountable digital framework for grievance redressal.

Its robust architecture, enforced workflows, and audit-ready design make it suitable for:

* ✔ Long-term deployment
* ✔ Future scalability
* ✔ Sustained administrative adoption

---

📌 *Developed for transparent, efficient, and accountable governance.*
