# Task Master

A modern, responsive To-Do web application built with Flask and SQLite.

## Features

- Add, update, and delete tasks
- Beautiful, modern UI with gradient backgrounds and smooth animations
- Responsive design for desktop and mobile
- Simple and clean codebase for easy learning and customization

## Screenshots

<!-- Add screenshots here after deployment -->

## Getting Started

### Prerequisites

- Python 3.7+
- pip

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/MuhammadAhmadF2005/flask_taskmaster.git
   cd flask_taskmaster
   ```

2. **Create and activate a virtual environment (optional but recommended):**
   ```bash
   python -m venv env
   # On Windows:
   env\Scripts\activate
   # On Mac/Linux:
   source env/bin/activate
   ```

3. **Install dependencies:**
   ```bash
   pip install flask flask_sqlalchemy
   ```

4. **Run the app:**
   ```bash
   python main.py
   ```

5. **Open your browser and go to:**
   ```
   http://127.0.0.1:5000/
   ```

## Project Structure

```
flask_taskmaster/
│
├── main.py              # Main Flask application
├── requirements.txt     # Python dependencies
├── Procfile            # For Heroku deployment
├── static/
│   └── css/
│       └── main.css    # Modern CSS styling
├── templates/
│   ├── base.html       # Base template
│   ├── index.html      # Main page template
│   └── update.html     # Update task template
├── instance/
│   └── test.db         # SQLite database
├── .gitignore          # Git ignore file
└── README.md           # This file
```

## Technologies Used

- **Backend**: Flask, SQLAlchemy
- **Database**: SQLite
- **Frontend**: HTML5, CSS3, Jinja2 Templates
- **Styling**: Modern CSS with gradients and animations

## Deployment

This app can be deployed to platforms like Heroku or Render. The `Procfile` is already included for Heroku deployment.

## License

This project is open source and available under the MIT License.

---

**Enjoy using Task Master!** 