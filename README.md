# Face Recognition Attendance System

A Python-based attendance management project that uses a webcam and face recognition to identify registered students and record attendance. The project includes a Flask web interface, SQLite database creation, attendance record viewing, and (in the more advanced versions) CSV export and email notifications.

## Features

- Register students with name, roll number, email, and a captured face encoding
- Recognize registered faces through a webcam
- Record attendance with date and time
- View attendance records through Flask templates
- Advanced version (`main.py`) supports filtering records and downloading attendance as CSV
- Optional email notifications when SMTP credentials are configured

## Project structure

```text
main/
├── app.py
├── app1.py
├── app2.py
├── main.py
├── create_db/
│   └── database.py
├── static/
│   ├── images/
│   └── attendance_logs/
├── templates/
└── requirements.txt
```

## Requirements

- Python 3.9–3.11 recommended
- Webcam
- Windows, macOS, or Linux (the `face-recognition` package may require additional native build dependencies, especially on Windows)

## Setup

1. Clone this repository and open the `main` folder:

   ```bash
   git clone <YOUR_GITHUB_REPOSITORY_URL>
   cd <REPOSITORY_FOLDER>/main
   ```

2. Create and activate a virtual environment:

   ```bash
   python -m venv .venv
   # Windows PowerShell
   .\.venv\Scripts\Activate.ps1
   # macOS/Linux
   source .venv/bin/activate
   ```

3. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. (Optional) Configure email notifications. Copy `.env.example` to `.env` and set your own values. Do not commit `.env`. The current scripts read environment variables; if you use a `.env` file, install `python-dotenv` and load it at the start of the selected script, or set the variables in your terminal.

   ```powershell
   $env:SENDER_EMAIL="your_email@gmail.com"
   $env:SENDER_PASSWORD="your_gmail_app_password"
   $env:ADMIN_EMAIL="admin_email@example.com"
   ```

5. Run the advanced Flask application:

   ```bash
   python main.py
   ```

6. Open `http://127.0.0.1:5000` in your browser. Allow webcam access when prompted by the application.

## Important notes

- The repository intentionally excludes local SQLite databases and captured attendance photos. The application creates its database when initialized.
- Use only test/student data that you have permission to process. Face images and face encodings are biometric personal data; do not publish them.
- Email notifications are optional and require your own Gmail app password. Never hardcode passwords or commit `.env` files.
- This is an academic project. Review and test the code and dependencies in your own environment before deployment.

## Author

Add your name, college, course, and project guide details here if you want them displayed on GitHub.
