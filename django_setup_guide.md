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


---

## 🐞 Debugging Django in Visual Studio Code (Windows, Debian, Arch)

Debugging Django applications in **Visual Studio Code (VS Code)** allows you to set breakpoints, inspect variables, and step through code during execution.  
Below are step-by-step guides for Windows, Debian, and Arch Linux.

---

### 🧰 1. Common Requirements for All Systems

- **Visual Studio Code** installed  
  Download from [https://code.visualstudio.com](https://code.visualstudio.com)
- **Python extension** for VS Code  
  📸 *Screenshot: VS Code Extensions tab → Search "Python" → Install*
- **Django project** already created and working

---

### 🪟 Windows Setup

1. **Activate your virtual environment**
   ```bash
   venv\Scripts\activate
   ```

2. **Open the project in VS Code**
   ```bash
   code .
   ```

3. **Install the Python extension**
   - Open the Extensions tab (`Ctrl+Shift+X`)
   - Search for **Python** and install the one by Microsoft  
     📸 *Screenshot: Python extension by Microsoft*

4. **Create the VS Code launch configuration**
   - Go to **Run and Debug** (icon on the left sidebar)
   - Click **"create a launch.json file"**
   - Choose **Django** from the list  
     📸 *Screenshot: Selecting Django in launch configuration*

   VS Code will generate a `.vscode/launch.json` file like this:

   ```json
   {
       "version": "0.2.0",
       "configurations": [
           {
               "name": "Python: Django",
               "type": "python",
               "request": "launch",
               "program": "${workspaceFolder}/manage.py",
               "args": [
                   "runserver",
                   "8000"
               ],
               "django": true
           }
       ]
   }
   ```

5. **Set breakpoints and start debugging**
   - Open a Django view or model file
   - Click left of the line number to set a breakpoint  
     📸 *Screenshot: Red breakpoint dot in VS Code editor*
   - Press `F5` to start debugging

---

### 🐧 Debian Setup

1. **Activate your virtual environment**
   ```bash
   source venv/bin/activate
   ```

2. **Install VS Code (or Code OSS)**
   ```bash
   sudo apt update
   sudo apt install code -y
   ```

3. **Install the Python extension**
   - Open VS Code → Extensions → Search *Python* → Install  
     📸 *Screenshot: Installing Python extension*

4. **Create launch configuration**
   - Click on the Run and Debug icon
   - Click **“create a launch.json file”**
   - Select **Django**

5. **Example launch.json**
   ```json
   {
       "version": "0.2.0",
       "configurations": [
           {
               "name": "Python: Django",
               "type": "python",
               "request": "launch",
               "program": "${workspaceFolder}/manage.py",
               "args": ["runserver", "0.0.0.0:8000"],
               "django": true
           }
       ]
   }
   ```

6. **Debugging**
   - Add breakpoints in `.py` files
   - Press `F5` to run the debugger
   - Open the browser at `http://127.0.0.1:8000`

---

### 🐉 Arch Linux Setup

1. **Activate virtual environment**
   ```bash
   source venv/bin/activate
   ```

2. **Install VS Code or Code OSS**
   ```bash
   sudo pacman -Syu code
   ```

3. **Install the Python extension**
   - Go to Extensions → Search “Python” → Install  
     📸 *Screenshot: Python extension installation on Arch*

4. **Create launch.json**
   - Open the **Run and Debug** tab
   - Click **"create a launch.json file"** → Select **Django**
   - Use this configuration:

   ```json
   {
       "version": "0.2.0",
       "configurations": [
           {
               "name": "Python: Django",
               "type": "python",
               "request": "launch",
               "program": "${workspaceFolder}/manage.py",
               "args": ["runserver"],
               "django": true,
               "justMyCode": true
           }
       ]
   }
   ```

5. **Run the debugger**
   - Press `F5` or click the **Run ▶️** button
   - Breakpoints will trigger when code executes

---

### ⚙️ Using Environment Variables for Debugging

You can load `.env` files automatically using VS Code’s integrated environment support.

1. **Install `python-dotenv`**
   ```bash
   pip install python-dotenv
   ```

2. **Create a `.env` file** in your project root:
   ```bash
   DEBUG=True
   SECRET_KEY=your_secret_key_here
   DATABASE_URL=sqlite:///db.sqlite3
   ```

3. **Update launch.json** to load environment variables:
   ```json
   {
       "version": "0.2.0",
       "configurations": [
           {
               "name": "Python: Django",
               "type": "python",
               "request": "launch",
               "program": "${workspaceFolder}/manage.py",
               "args": ["runserver"],
               "django": true,
               "envFile": "${workspaceFolder}/.env"
           }
       ]
   }
   ```

   📸 *Screenshot: launch.json using envFile setting*

---

### 🧩 Using django-debug-toolbar (Optional)

For advanced debugging in the browser:

1. **Install it**
   ```bash
   pip install django-debug-toolbar
   ```

2. **Add to INSTALLED_APPS** in `settings.py`
   ```python
   INSTALLED_APPS = [
       ...
       'debug_toolbar',
   ]
   ```

3. **Add middleware**
   ```python
   MIDDLEWARE = [
       'debug_toolbar.middleware.DebugToolbarMiddleware',
       ...
   ]
   ```

4. **Configure internal IPs (for localhost)**
   ```python
   INTERNAL_IPS = [
       "127.0.0.1",
   ]
   ```

5. **Include the toolbar URLs**
   ```python
   from django.conf import settings
   from django.urls import include, path

   if settings.DEBUG:
       urlpatterns += [path('__debug__/', include('debug_toolbar.urls'))]
   ```

   📸 *Screenshot: Django Debug Toolbar in browser*

---

### ✅ Summary

You now have a fully configured Django debugging setup in Visual Studio Code for **Windows**, **Debian**, and **Arch Linux**.  
This configuration supports:
- Breakpoints
- Environment variable management
- Optional Django Debug Toolbar integration



---

## 🧭 Cloning and Running an Existing Django Project (Windows, Debian, Arch)

If you’re working on an existing Django project from a Git repository, you can quickly set it up locally on your system.  
This guide explains how to do it on **Windows**, **Debian**, and **Arch Linux**.

---

### 🪟 Windows Setup

1. **Install Git (if not installed yet)**
   - Download from [https://git-scm.com/downloads](https://git-scm.com/downloads)
   - During installation, select *“Add Git to PATH”*  
     📸 *Screenshot: Git installer option "Add Git to PATH"*

2. **Clone the repository**
   ```bash
   git clone https://github.com/username/project-name.git
   cd project-name
   ```

3. **Create and activate a virtual environment**
   ```bash
   python -m venv venv
   venv\Scripts\activate
   ```

4. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

5. **Apply database migrations**
   ```bash
   python manage.py migrate
   ```

6. **Create a superuser (optional)**
   ```bash
   python manage.py createsuperuser
   ```

7. **Run the server**
   ```bash
   python manage.py runserver
   ```

   📸 *Screenshot: Django development server running on Windows PowerShell*

8. **Access the project**
   Open [http://127.0.0.1:8000](http://127.0.0.1:8000) in your browser.

9. **(Optional) Create a `.env` file**
   If your project uses environment variables:
   ```bash
   DEBUG=True
   SECRET_KEY=your_secret_key_here
   DATABASE_URL=sqlite:///db.sqlite3
   ```

---

### 🐧 Debian Setup

1. **Install Git and Python tools**
   ```bash
   sudo apt update
   sudo apt install git python3 python3-venv python3-pip -y
   ```

2. **Clone the repository**
   ```bash
   git clone https://github.com/username/project-name.git
   cd project-name
   ```

3. **Create and activate virtual environment**
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

4. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

5. **Apply database migrations**
   ```bash
   python manage.py migrate
   ```

6. **Create a superuser (optional)**
   ```bash
   python manage.py createsuperuser
   ```

7. **Run the Django server**
   ```bash
   python manage.py runserver 0.0.0.0:8000
   ```

   📸 *Screenshot: Django server running in Debian terminal*

8. **Access the project**
   Open [http://127.0.0.1:8000](http://127.0.0.1:8000)

9. **(Optional) Create a `.env` file**
   ```bash
   DEBUG=True
   SECRET_KEY=your_secret_key_here
   DATABASE_URL=sqlite:///db.sqlite3
   ```

---

### 🐉 Arch Linux Setup

1. **Install Git and Python tools**
   ```bash
   sudo pacman -Syu git python python-pip
   ```

2. **Clone the repository**
   ```bash
   git clone https://github.com/username/project-name.git
   cd project-name
   ```

3. **Create and activate a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate
   ```

4. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

5. **Apply database migrations**
   ```bash
   python manage.py migrate
   ```

6. **Create a superuser (optional)**
   ```bash
   python manage.py createsuperuser
   ```

7. **Start the development server**
   ```bash
   python manage.py runserver
   ```

   📸 *Screenshot: Django server running on Arch terminal*

8. **Access the project**
   Open [http://127.0.0.1:8000](http://127.0.0.1:8000)

9. **(Optional) Add environment variables**
   Create a `.env` file in the root folder:
   ```bash
   DEBUG=True
   SECRET_KEY=your_secret_key_here
   DATABASE_URL=sqlite:///db.sqlite3
   ```

---

### ⚙️ Common Issues and Fixes

| Problem | Possible Cause | Solution |
|----------|----------------|-----------|
| `ModuleNotFoundError` | Dependencies not installed | Run `pip install -r requirements.txt` |
| `django.core.exceptions.ImproperlyConfigured` | Missing `.env` or environment variables | Add `.env` and configure settings |
| `sqlite3.OperationalError` | Database not migrated | Run `python manage.py migrate` |
| Port already in use | Another app running on port 8000 | Run `python manage.py runserver 8080` |

---

### ✅ Summary

You now know how to **clone**, **configure**, and **run** a Django project on **Windows**, **Debian**, and **Arch Linux**.  
This process ensures a consistent environment across different systems and allows collaboration through Git repositories.

