# Django Project Setup Guide

This document explains how to set up and start a Django project on **Windows**, **Debian**, and **Arch Linux**, including installation requirements and essential commands.

---

## 🧩 Requirements

### Common Requirements
- **Python 3.10+** (recommended 3.12 or newer)
- **pip** (Python package manager)
- **virtualenv** (for isolated environments)

---

## 🪟 Windows Setup

### 1. Install Python
1. Download from [python.org/downloads](https://www.python.org/downloads/)
2. During installation, **check** the option:
   - ✅ *Add Python to PATH*
3. Verify installation:
   ```bash
   python --version
   pip --version
   ```

### 2. Create a Virtual Environment
```bash
python -m venv venv
venv\Scripts\activate
```

### 3. Install Django
```bash
pip install django
```

### 4. Verify Django Installation
```bash
python -m django --version
```

---

## 🐧 Debian Setup

### 1. Install Python and pip
```bash
sudo apt update
sudo apt install python3 python3-venv python3-pip -y
```

### 2. Create and Activate Virtual Environment
```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Django
```bash
pip install django
```

### 4. Verify Installation
```bash
python -m django --version
```

---

## 🐉 Arch Linux Setup

### 1. Install Python and pip
```bash
sudo pacman -Syu python python-pip
```

### 2. Create and Activate Virtual Environment
```bash
python -m venv venv
source venv/bin/activate
```

### 3. Install Django
```bash
pip install django
```

### 4. Verify Installation
```bash
python -m django --version
```

---

## 🚀 Start a New Django Project

### 1. Create a Project
```bash
django-admin startproject myproject
cd myproject
```

### 2. Run Development Server
```bash
python manage.py runserver
```

Then open your browser at: [http://127.0.0.1:8000](http://127.0.0.1:8000)

---

## ⚙️ Common Django Commands

| Command | Description |
|----------|--------------|
| `django-admin startproject projectname` | Creates a new project |
| `python manage.py startapp appname` | Creates a new app inside the project |
| `python manage.py runserver` | Starts the local development server |
| `python manage.py makemigrations` | Detects model changes and creates migration files |
| `python manage.py migrate` | Applies migrations to the database |
| `python manage.py createsuperuser` | Creates an admin user |
| `python manage.py shell` | Opens a Python shell within Django context |
| `python manage.py test` | Runs tests |
| `python manage.py collectstatic` | Collects static files for deployment |

---

## 🧰 Tips

- Always **activate your virtual environment** before running Django commands.
- Use `.env` files to store environment variables securely.
- Use **requirements.txt** to share dependencies:
  ```bash
  pip freeze > requirements.txt
  ```
- Install dependencies from file:
  ```bash
  pip install -r requirements.txt
  ```

---

## ✅ Conclusion

You now have Django installed and can start developing your applications across **Windows**, **Debian**, and **Arch Linux** systems!
