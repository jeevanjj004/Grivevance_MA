🏛️ Grievance Management System (GMS)

Project Overview, Architecture & Workflow Documentation

The Grievance Management System (GMS) is a centralized, web-based administrative platform designed to digitally manage public grievances submitted to district administrations.

It enables structured intake, controlled assignment, continuous monitoring, and accountable resolution of grievances through clearly defined administrative roles and workflows.

The platform consolidates grievances from multiple channels into a single system, ensuring every grievance is traceable, time-bound, and audit-ready.

📌 1. Problem Statement & Solution
❌ Problems Addressed

Fragmented grievance submissions across multiple channels

Manual tracking and delayed grievance resolution

Lack of accountability and administrative visibility

Absence of structured deadline enforcement

Limited auditability of grievance handling

✅ System Solution

Centralized grievance intake and tracking

Role-based assignment and monitoring

Automatic priority-based deadline management

Enforced accountability through system controls

Complete audit trail for administrative review

👥 2. Users & Privilege Hierarchy

The system enforces a strict Role-Based Access Control (RBAC) model.

🔑 User Roles

System Administrator

District Collector

District Officer

Head of Department (HOD)

Department Officers

Public Users

Petition Entry Users

🛂 3. Privilege Details
Role	Privileges
System Administrator	Full system access, configuration, and technical maintenance
District Collector	District-wide access, priority control, monitoring, and administrative orders
District Officer	District-level oversight excluding sensitive operations
Head of Department (HOD)	Department control, officer assignment, and performance supervision
Department Officers	Grievance execution, updates, and inter-department requests
Public Users	Grievance submission, document upload, and tracking
Petition Entry Users	Digitization and entry of physical petitions

🔐 Sensitive actions require OTP and password verification

🗄️ 4. Database Design Overview

The system uses a normalized relational database implemented with MySQL.

📦 Core Tables

User

PublicUserProfile

District

Department

CollectorProfile

DistrictOfficerProfile

OfficerProfile

IDTrackers

Grievance

🔄 Workflow Tables

GrievanceAssignment

GrievanceFlow

FlowStage

GrievanceStatusLog

GrievanceTransfer

⚡ Indexes are applied on status, priority, and due dates for optimized reporting and performance.

🛠️ 5. Technology Stack

Frontend: HTML, CSS, JavaScript

Backend: Django (Python) – MVT Architecture

Database: MySQL

Integrations:

Facebook Graph API

WhatsApp API

🔁 6. Detailed Workflow
📝 6.1 Grievance Registration

Grievances submitted via Web Portal, WhatsApp, Facebook, or Office Entry

Unique grievance ID auto-generated

Automatic district and department mapping

🏷️ 6.2 Classification & Priority

Automatic priority assignment based on grievance type

Due date calculated automatically

Priority modification allowed for District Collector

🏢 6.3 Department Assignment

HOD assigns grievances to department officers

Assignment logged with timestamps

👨‍💼 6.4 Officer Action & Updates

Officers update grievance status periodically

Updates visible to higher authorities and public users

🔀 6.5 Inter-Department Transfer

Officer initiates transfer request

HOD approval required

Complete transfer history maintained

⏰ 6.6 Deadline Enforcement

Automated reminders before due date

Mandatory justification required for overdue grievances

✅ 6.7 Resolution & Closure

Grievances marked as Resolved or Rejected

Full grievance lifecycle retained for audit purposes

🔐 7. Security Mechanisms

Secure authentication and session management

Role-based access enforcement

OTP-based authorization for sensitive actions

Dual authorization during Collector–District Officer handover

Audit logging for all critical system operations

⭐ 8. Key Features

Multi-channel grievance intake

Role-specific dashboards

Priority-based deadline management

SMS and email acknowledgements

Grievance tracking using unique ID

Filtered and exportable reports

Administrative order management

🧾 9. Conclusion

The Grievance Management System provides a structured, secure, and accountable digital framework for grievance redressal.

Its robust data model, enforced workflows, deadline accountability, and audit-ready architecture make it ideal for long-term deployment, future expansion, and sustained administrative adoption.

⚠️ Warnings & Security Notes

API Keys & Tokens:
This project integrates Facebook Graph API and WhatsApp API.
🚫 Never expose API keys in the repository.
✅ Store them securely using .env files or environment variables.

Potential Errors:
Missing or incorrect API keys may cause runtime errors.

Sensitive Data:
Do not commit real user data or credentials to the repository.

💻 Installation & Setup
# Clone the repository
git clone https://github.com/jeevanjj004/Grivevance_MA.git

# Navigate to the project directory
cd Grivevance_MA

# Create a virtual environment
python -m venv venv

# Activate the virtual environment
# Windows
venv\Scripts\activate

# Linux / macOS
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Create database migrations
python manage.py makemigrations

# Apply migrations
python manage.py migrate

# Run the development server
python manage.py runserver

# Open in browser
http://127.0.0.1:8000/
