# 🏫 SOS – School of Skills Management Portal

A modern **Educational Institution Management Portal** built using **Python, Streamlit, Pandas, and Object-Oriented Programming (OOP)**.

The system provides a centralized interface for managing students, courses, employees, enrollments, attendance, fees, reports, and institutional information.

---

## 🚀 Project Overview

**SOS – School of Skills Management Portal** is designed to simplify and digitize the day-to-day administrative operations of an educational institution.

The application features a responsive **Red / Black / White** interface and provides separate modules for different institutional activities.

The project also includes a dedicated OOP backend containing models for:

- Institution
- Course
- Student
- Employee
- Faculty
- Academic Services

The OOP layer includes validation, enrollment management, fee management, course capacity management, and reusable service functions.

---

## ✨ Key Features

### 📊 Dashboard
- Total students
- Total employees
- Total courses
- Total enrollments
- Student attendance overview
- Employee attendance overview
- Course-wise enrollment chart
- Recent activity log
- Quick navigation actions

### 🏛️ Institution Management
- Institution information
- Location and contact details
- Departments
- Institution overview

### 🎓 Student Management
- Register new students
- View all students
- Search students by ID or name
- Student profile
- Course assignment
- Admission information
- Fee status
- Attendance overview

### 📚 Course Management
- View all courses
- Add new courses
- Course ID and name
- Duration
- Credits
- Maximum capacity
- Assigned faculty
- Department
- Search courses
- View enrolled students
- Available seat calculation

### 👨‍🏫 Employee Management
- Add employees
- View employee information
- Department management
- Designation
- Specialization
- Employment type
- Joining date
- Assigned courses
- Employee search

### 📝 Enrollment Management
- Enroll students into courses
- Drop students from courses
- Course capacity validation
- Enrollment tracking
- Prevention of duplicate enrollment

The backend maintains enrollment consistency between students and courses through `AcademicServices`.

### 📅 Student Attendance
- Mark attendance
- Present / Absent / Leave status
- Attendance history
- Attendance editing
- Student attendance percentage
- Attendance summary
- Attendance charts

### 👥 Employee Attendance
- Employee attendance management
- Attendance records
- Attendance summaries

### 💰 Fee Management
- Total fee tracking
- Paid amount
- Pending amount
- Payment recording
- Paid / Partially Paid / Pending status
- Payment validation
- Prevention of overpayment

The application calculates pending fees from **Total Fee − Paid**, rather than storing a separate pending value, helping prevent inconsistent fee data.

### 📊 Reports & Analytics
Available reports include:

- Student Report
- Employee Report
- Course Report
- Student Attendance Report
- Employee Attendance Report
- Enrollment Report
- Fee Report

Reports include tables, filters, and visual charts.

### ⚙️ Administration
- System data overview
- Institution branding information
- Session data management
- Reset portal to sample data

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Streamlit | Web application framework |
| Pandas | Data processing and tables |
| OOP | Application architecture |
| HTML/CSS | UI customization |
| Regex | Email validation |
| Datetime | Date and attendance management |

---

## 📁 Project Structure

```text
SOS-School-of-Skills/
│
├── app.py
├── institution.py
├── README.md
└── requirements.txt
```

### `app.py`

Main Streamlit application containing:

- User interface
- Dashboard
- Navigation
- Student management
- Course management
- Employee management
- Enrollment
- Attendance
- Fees
- Reports
- Administration

The application uses Streamlit session state to maintain the portal's data during a session.

### `institution.py`

Contains the reusable OOP/domain layer including:

- `SOSInstitution`
- `Course`
- `Student`
- `Employee`
- `Faculty`
- `AcademicServices`

It also contains demo data generation and self-tests.

---

## 🧠 Object-Oriented Programming

The project demonstrates several OOP concepts.

### Encapsulation

Fee information is controlled through properties and validated methods such as:

```python
student.paid_fee
student.pending_fee
student.record_payment()
```

The actual paid amount is protected through `_paid_fee`.

### Inheritance

`Faculty` inherits from `Employee`:

```python
class Faculty(Employee):
    ...
```

This allows faculty members to reuse employee functionality while maintaining a separate faculty type.

### Abstraction

`AcademicServices` provides high-level operations such as:

```python
AcademicServices.enroll_student()
AcademicServices.drop_course()
```

This separates business logic from the user interface.

### Data Validation

The system validates:

- Email addresses
- Course capacity
- Duplicate IDs
- Payment amounts
- Overpayments
- Duplicate enrollment
- Maximum courses per student

The backend defines a maximum of **3 courses per student**.

---

## 🎨 UI Design

The application uses a custom **Red / Black / White** theme.

### Design Features

- Dark dashboard
- Red accent color
- Custom SOS branding
- KPI cards
- Sidebar navigation
- Responsive columns
- Interactive tabs
- Data tables
- Charts
- Expandable student/course profiles

The application defines custom CSS styling for the Streamlit interface and uses the SOS logo from the institution website.

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/sos-school-of-skills.git
```

### 2. Open the project

```bash
cd sos-school-of-skills
```

### 3. Create a virtual environment

#### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

#### macOS / Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

### 4. Install dependencies

```bash
pip install streamlit pandas
```

Or, if you have a `requirements.txt` file:

```bash
pip install -r requirements.txt
```

### 5. Run the application

```bash
streamlit run app.py
```

The application will open in your browser.

---

## 📦 Requirements

Create a `requirements.txt` file containing:

```text
streamlit
pandas
```

---

## 🧪 Backend Testing

The `institution.py` module includes built-in self-tests covering:

- Fee calculations
- Payment validation
- Overpayment prevention
- Course enrollment
- Course dropping
- Enrollment consistency

Run:

```bash
python institution.py
```

A successful test run prints:

```text
All institution.py self-tests passed — no errors.
```

The self-test logic is included directly in the backend module.

---

## 📸 Main Modules

```text
🏠 Dashboard
│
├── 🏛️ Institution
├── 🎓 Students
├── 📚 Courses
├── 👨‍🏫 Employees
├── 📝 Enrollment
├── 📅 Student Attendance
├── 👥 Employee Attendance
├── 💰 Fees
├── 📊 Reports
└── ⚙️ Administration
```

---

## 🔐 Data Handling

This version primarily uses **Streamlit session state and in-memory data**.

Therefore:

> Data entered during a session is not intended to function as permanent database storage.

The Administration module provides an option to reset the current portal session back to sample data.

For production deployment, the application could be extended with:

- MySQL
- PostgreSQL
- SQLite
- Firebase
- MongoDB
- Authentication
- Role-based access control
- Persistent cloud storage

---

## 🔮 Future Improvements

Potential future upgrades include:

- 🔐 User authentication
- 👤 Admin / Faculty / Student roles
- 🗄️ Database integration
- 📧 Email notifications
- 📱 Mobile-friendly interface
- 📄 PDF report generation
- 💳 Online fee payments
- 📈 Advanced analytics dashboard
- 🔔 Attendance alerts
- 📅 Timetable management
- 📝 Examination management
- 📚 Assignment management
- ☁️ Cloud deployment
- 🔑 Secure login and authorization

---

## 🎯 Project Objectives

The main objectives of this project are to:

1. Digitize educational institution administration.
2. Reduce manual record management.
3. Demonstrate practical Python programming.
4. Apply Object-Oriented Programming concepts.
5. Provide interactive data visualization.
6. Simplify student and course management.
7. Improve attendance and fee tracking.
8. Demonstrate a real-world Streamlit application.

---

## 👨‍💻 Author

**Adul Ahamed Kt**

BBA (Information Technology)  
Lovely Professional University

### Areas of Interest

- Python
- Data Analytics
- Business Analytics
- Artificial Intelligence
- Digital Marketing
- Software Development

---

## 📄 License

This project is intended for **educational and academic purposes**.

You are free to modify and extend the project for learning and development.

---

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.

**Built with ❤️ using Python and Streamlit.**
