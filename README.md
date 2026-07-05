# Django_Feedback_Project

**A simple feedback system built with Django, designed to help users provide and manage their feedback efficiently.**

[![Python](https://img.shields.io/badge/python-3.x-blue.svg)] [![License](https://img.shields.io/github/license/PartORG/Django_Feedback_Project?color=green)] [![Package Manager](https://img.shields.io/badge/package-manager-pip-green)] [![Framework](https://img.shields.io/badge/framework-Django-green)] [![Testing](https://img.shields.io/badge/testing-None-red)]

Django_Feedback_Project is a straightforward Django application that allows users to submit and manage feedback. It provides a user-friendly interface for both submitting new feedback and viewing existing feedback.

## Table of Contents

1. [Features](#features)
2. [How It Works](#how-it-works)
3. [Technology Stack](#technology-stack)
4. [Requirements](#requirements)
5. [Installation](#installation)
6. [Configuration](#configuration)
7. [Quick Start](#quick-start)
8. [Usage](#usage)
9. [Project Structure](#project-structure)
10. [Development](#development)
11. [Limitations](#limitations)
12. [License](#license)

## Features

### User Feedback Submission
- **What it does:** Allows users to submit feedback easily.
- **Why it exists:** To provide a platform for users to share their thoughts and suggestions.
- **Why it is useful:** Facilitates better communication between users and administrators.

### Feedback Management
- **What it does:** Enables administrators to view, edit, and delete submitted feedback.
- **Why it exists:** To ensure that all feedback is properly managed and addressed.
- **Why it is useful:** Improves the efficiency of handling user feedback.

## How It Works

Django_Feedback_Project follows a simple workflow:

1. Users can submit feedback through a form on the website.
2. The submitted feedback is stored in a database.
3. Administrators can view, edit, and delete feedback from the admin panel.

Here's an ASCII diagram illustrating the workflow:

```
User submits feedback -> Feedback stored in database -> Administrator views feedback
```

## Technology Stack

| Technology | Purpose |
|------------|---------|
| Django     | Web framework for building robust web applications. |
| Python     | Programming language used to develop the application. |
| HTML/CSS   | Frontend technologies for creating user interfaces. |

## Requirements

- Python 3.x
- Django 4.x

## Installation

To install Django_Feedback_Project, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/PartORG/Django_Feedback_Project.git
    ```

2. Navigate to the project directory:
    ```bash
    cd Django_Feedback_Project
    ```

3. Create a virtual environment and activate it:
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

4. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

5. Run migrations:
    ```bash
    python manage.py migrate
    ```

6. Create a superuser (for admin access):
    ```bash
    python manage.py createsuperuser
    ```

7. Start the development server:
    ```bash
    python manage.py runserver
    ```

## Configuration

The project uses environment variables for configuration. The following environment variables are observed:

- `SECRET_KEY`: Django secret key.
- `DEBUG`: Debug mode flag.

These variables can be set in a `.env` file or directly in the operating system environment.

## Quick Start

To quickly start using Django_Feedback_Project, follow these steps:

1. Clone the repository and navigate to the project directory.
2. Create and activate a virtual environment.
3. Install dependencies.
4. Run migrations.
5. Create a superuser.
6. Start the development server.

Example commands:
```bash
git clone https://github.com/PartORG/Django_Feedback_Project.git
cd Django_Feedback_Project
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
pip install -r requirements.txt
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

## Usage

To submit feedback, navigate to the website and fill out the feedback form. To view or manage feedback, log in as an administrator.

Example commands:
```bash
# Submitting feedback
curl -X POST http://127.0.0.1:8000/submit_feedback/ \
-H "Content-Type: application/json" \
-d '{"user": "JohnDoe", "feedback": "Great service!"}'

# Viewing feedback (as an admin)
python manage.py shell
from profiles.models import Feedback
Feedback.objects.all()
```

## Project Structure

```plaintext
Django_Feedback_Project/
├── README.md
├── db.sqlite3
├── feedback/
│   ├── __init__.py
│   ├── __pycache__/
│   │   ├── __init__.cpython-310.pyc
│   │   ├── settings.cpython-310.pyc
│   │   ├── urls.cpython-310.pyc
│   │   └── wsgi.cpython-310.pyc
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── manage.py
├── profiles/
│   ├── __init__.py
│   ├── __pycache__/
│   │   ├── __init__.cpython-310.pyc
│   │   ├── admin.cpython-310.pyc
│   │   ├── apps.cpython-310.pyc
│   │   ├── forms.cpython-310.pyc
│   │   ├── models.cpython-310.pyc
│   │   ├── urls.cpython-310.pyc
│   │   └── views.cpython-310.pyc
│   ├── admin.py
│   ├── apps.py
│   ├── forms.py
│   ├── migrations/
│   │   ├── 0001_initial.py
│   │   ├── __init__.py
│   │   ├── __pycache__/
│   │   │   ├── 0001_initial.cpython-310.pyc
│   │   │   └── __init__.cpython-310.pyc
│   ├── models.py
│   ├── static/
│   │   └── profiles/
│   │       └── styles.css
│   ├── templates/
│   │   └── profiles/
│   │       ├── create_profile.html
│   │       └── user_profiles.html
│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── reviews/
│   ├── __init__.py
│   ├── __pycache__/
│   │   ├── __init__.cpython-310.pyc
│   │   ├── admin.cpython-310.pyc
│   │   ├── apps.cpython-310.pyc
│   │   ├── forms.cpython-310.pyc
│   │   ├── models.cpython-310.pyc
│   │   ├── urls.cpython-310.pyc
│   │   └── views.cpython-310.pyc
│   ├── admin.py
│   ├── apps.py
│   ├── forms.py
│   ├── migrations/
│   │   ├── 0001_initial.py
│   │   ├── __init__.py
│   │   ├── __pycache__/
│   │   │   ├── 0001_initial.cpython-310.pyc
│   │   │   └── __init__.cpython-310.pyc
│   ├── models.py
│   ├── static/
│   │   └── reviews/
│   │       └── styles.css
│   ├── templates/
│   │   └── reviews/
│   │       ├── base.html
│   │       ├── review.html
│   │       ├── review_list.html
│   │       ├── single_review.html
│   │       └── thank_you.html
│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── temp/
│   └── image.png
└── uploads/
    └── images/
        ├── bizztrack_logo.png
        └── red.png
```

## Development

The development workflow involves:

1. Cloning the repository.
2. Setting up a virtual environment.
3. Installing dependencies.
4. Running migrations.
5. Creating a superuser.
6. Starting the development server.

## Limitations

- The project does not include automated testing.
- No continuous integration setup is provided.

## License

Django_Feedback_Project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.