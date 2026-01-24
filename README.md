# Grievance Management System
Centralized complaint management platform for public services, enabling citizens to submit complaints via website, WhatsApp, and Facebook APIs, with automated routing and tracking for the Idukki Collectorate.

---

## 🚀 Features
- **Complaint Submission:** Users can submit complaints through the website, WhatsApp, and Facebook APIs  
- **Automated Routing:** Complaints are automatically assigned to the appropriate department or officer  
- **Status Tracking:** Citizens can track the status of their complaints in real-time  
- **Dashboard:** Interactive dashboard for officials with filters, search, and sorting  
- **Reports:** Export complaint reports in PDF and Excel formats  
- **Notifications:** Automatic updates for departments and citizens regarding complaint status  

---

## 🛠️ Tech Stack
- **Backend:** Python, Django  
- **Database:** MySQL  
- **Frontend:** HTML, CSS, JavaScript, Bootstrap  
- **Other:** WhatsApp API, Facebook API for complaint submission and notifications  

---

## 💻 Installation / Setup
```bash
# Clone the repository
git clone https://github.com/jeevanjj004/Grivevance_MA.git

# Navigate to project folder
cd Grivevance_MA

# Create a virtual environment
python -m venv venv

# Activate the virtual environment
# Windows
venv\Scripts\activate
# Linux / Mac
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Make migrations
python manage.py makemigrations

# Apply migrations
python manage.py migrate

# Run the development server
python manage.py runserver

# Open in browser
http://127.0.0.1:8000/
