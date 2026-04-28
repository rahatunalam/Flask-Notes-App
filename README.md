# 📝 Flask Notes App

A simple full-stack web application for creating and managing personal notes, built with Flask and SQLite.

## Features

- **User Authentication** — Register, log in, and log out securely
- **Personal Notes** — Add and delete your own notes
- **Session Persistence** — Stay logged in across browser sessions
- **Flash Messaging** — Real-time feedback for user actions
- **Responsive UI** — Built with Bootstrap 4

## Tech Stack

| Layer      | Technology                          |
|------------|-------------------------------------|
| Backend    | Python, Flask                       |
| Database   | SQLite via Flask-SQLAlchemy         |
| Auth       | Flask-Login, Werkzeug password hash |
| Frontend   | Jinja2 templates, Bootstrap 4       |
| JS         | Vanilla JavaScript (Fetch API)      |

## Project Structure

```
project/
│
├── main.py                  # App entry point
│
└── website/
    ├── __init__.py          # App factory & DB initialization
    ├── models.py            # User and Note database models
    ├── auth.py              # Login, logout, sign-up routes
    ├── views.py             # Home and note management routes
    │
    ├── static/
    │   └── index.js         # Delete note (Fetch API)
    │
    └── templates/
        ├── base.html        # Shared layout & navbar
        ├── home.html        # Notes dashboard
        ├── login.html       # Login form
        └── sign_up.html     # Registration form
```

## Getting Started

### Prerequisites

- Python 3.7+
- pip

### Installation

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd <project-folder>
   ```

2. **Create and activate a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate      # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install flask flask-sqlalchemy flask-login werkzeug
   ```

4. **Run the app**
   ```bash
   python main.py
   ```

5. **Open in your browser**

The SQLite database (`database.db`) is created automatically inside the `website/` folder on first run.

## Usage

1. Navigate to `/sign-up` to create an account
2. Log in at `/login`
3. Add notes from the home page
4. Delete any note using the **×** button next to it
5. Log out via the navbar

## Database Models

**User**
- `id` — Primary key
- `email` — Unique email address
- `password` — Hashed password (pbkdf2:sha256)
- `first_name` — Display name
- `notes` — Relationship to user's notes

**Note**
- `id` — Primary key
- `data` — Note content (up to 10,000 characters)
- `date` — Timestamp (auto-set)
- `user_id` — Foreign key to User

## Known Issues & Suggested Improvements
- **Input sanitization:** Consider adding server-side sanitization for note content.
- **Pagination:** Add pagination to the notes list for users with many notes.

## License

This project is open source and available under the [MIT License](LICENSE).
