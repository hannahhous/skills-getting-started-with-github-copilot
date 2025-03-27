# Mergington High School Activities Manager

This project is a web application for managing extracurricular activities at Mergington High School.

## Project Structure
- **`src/`**: Contains the main application code.
  - **`app.py`**: A FastAPI application that serves as the backend API.
  - **`static/`**: Contains frontend assets.
    - **`index.html`**: The main HTML file for the web interface.
    - **`app.js`**: JavaScript for dynamic functionality, such as fetching activities and handling form submissions.
    - **`styles.css`**: CSS for styling the web interface.
- **`.github/`**: Contains GitHub Actions workflows and step-by-step instructions for the exercise.
- **`.vscode/`**: Configuration for debugging in Visual Studio Code.
- **`.devcontainer/`**: Configuration for the development container, including dependencies and extensions.
- **`requirements.txt`**: Lists Python dependencies (`fastapi`, `uvicorn`).

## Features

- View all available extracurricular activities
- Sign up for activities

## Steps to Run the Project
1. **Install Dependencies**:
   Make sure you have Python installed. Then, run:
   ```bash
   pip install -r requirements.txt
   ```

2. **Run the Application**:
   Start the FastAPI application:
   ```bash
   python src/app.py
   ```

3. **Access the Web Interface**:
   Open your browser and navigate to:
   ```
   http://localhost:8000/static/index.html
   ```

4. **API Documentation**:
   - Swagger UI: [http://localhost:8000/docs](http://localhost:8000/docs)
   - Redoc: [http://localhost:8000/redoc](http://localhost:8000/redoc)

## API Endpoints

| Method | Endpoint                                                          | Description                                                         |
| ------ | ----------------------------------------------------------------- | ------------------------------------------------------------------- |
| GET    | `/activities`                                                     | Get all activities with their details and current participant count |
| POST   | `/activities/{activity_name}/signup?email=student@mergington.edu` | Sign up for an activity                                             |

## Data Model

The application uses a simple data model with meaningful identifiers:

1. **Activities** - Uses activity name as identifier:

   - Description
   - Schedule
   - Maximum number of participants allowed
   - List of student emails who are signed up

2. **Students** - Uses email as identifier:
   - Name
   - Grade level

All data is stored in memory, which means data will be reset when the server restarts.
