# Hospital Management System (HMS)

This Hospital Management System is a web-based application designed to manage hospital-related data efficiently, including patients, doctors, and appointments. The application is built using **Flask** and incorporates functionalities such as user authentication, patient booking, doctor management, and more.

---

## Features

### User Authentication
- **Signup**: Allows users to create accounts.
- **Login**: Secure login system with encrypted passwords using `Werkzeug`.
- **Logout**: Users can log out securely.

### User Roles
- **Admin**: Full access to the system.
- **Doctor**: Can view all patient bookings.
- **Patient**: Can manage their bookings.

### Patient Management
- Book, view, edit, and delete appointments.
- View available doctors and departments.
- Receive booking confirmation (optional email integration).

### Doctor Management
- Add and manage doctor details, including department and contact information.
- Search functionality to find doctors by name or department.

### Database Management
- Tables for **Users**, **Patients**, **Doctors**, **Triggers**, and **Tests**.
- Seamless integration with **MySQL** using SQLAlchemy.

### Error Handling
- Flash messages for feedback during operations (e.g., booking confirmation, login issues).

### Triggers and Logs
- View and monitor system actions through a dedicated page.

---

## Tech Stack

### Backend
- Flask
  - Flask-Login: User authentication and session management.
  - SQLAlchemy: ORM for database operations.
  - Flask-Mail: Email functionality (optional, commented out in code).

### Frontend
- HTML
- CSS
- JavaScript (if applicable)

### Database
- MySQL

---

## Installation

### Prerequisites
- Python 3.x
- MySQL server
- pip (Python package manager)

### Steps
1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```
2. Navigate to the project directory:
   ```bash
   cd hospital-management-system
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Configure the database:
   - Update `app.config['SQLALCHEMY_DATABASE_URI']` with your MySQL credentials and database name.
   - Example:
     ```python
     app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql://root:password@localhost/hms'
     ```
5. Create the database and tables:
   ```bash
   flask shell
   >>> from app import db
   >>> db.create_all()
   >>> exit()
   ```
6. Run the application:
   ```bash
   python app.py
   ```
7. Open your browser and navigate to:
   ```
   http://127.0.0.1:5000/
   ```

---

## Usage

### 1. **Sign Up**
   - Navigate to the signup page.
   - Create an account as a patient, doctor, or admin.
   
### 2. **Log In**
   - Log in using the registered email and password.
   - Access features based on user role.

### 3. **Manage Appointments**
   - Patients can book, view, edit, or delete their appointments.
   - Doctors can view all appointments.

### 4. **Search Doctors**
   - Use the search bar on the homepage to find doctors by name or department.

---

## Folder Structure

```
hospital-management-system/
│
├── templates/             # HTML templates for pages
├── static/                # Static files (CSS, JS, images)
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
└── README.md              # Project documentation
```

---

## Optional Configuration

### Email Integration
- To enable email notifications, uncomment the `Flask-Mail` configuration in `app.py` and replace the placeholders with your SMTP credentials:
  ```python
  app.config.update(
      MAIL_SERVER='smtp.gmail.com',
      MAIL_PORT='465',
      MAIL_USE_SSL=True,
      MAIL_USERNAME="your-email@gmail.com",
      MAIL_PASSWORD="your-email-password"
  )
  ```

---

## Contributing
Contributions are welcome! Feel free to submit issues or pull requests.

---

## License
This project is licensed under the MIT License. 

---

## Acknowledgments
- Flask Documentation: https://flask.palletsprojects.com/
- SQLAlchemy Documentation: https://docs.sqlalchemy.org/
