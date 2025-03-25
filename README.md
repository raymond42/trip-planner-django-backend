# Trip Planner API Backend

This is the backend for the Trip Planner application, built using **Django** for the API and deployed on **Railway.app**. The API provides functionalities to handle trip-related data, user management, and other features required for the trip planning process.

## Table of Contents

- [Installation](#installation)
- [Requirements](#requirements)
- [Setup](#setup)
- [Environment Variables](#environment-variables)
- [Running the Project](#running-the-project)
- [Deployment](#deployment)
- [Usage](#usage)
- [Troubleshooting](#troubleshooting)
- [License](#license)

## Installation

To run this backend locally, you need to have Python 3.13 or higher installed. Follow these steps to get started:

1. **Clone the repository**:

   ```bash
   git clone https://github.com/your-username/trip-planner-api.git
   cd trip-planner-api
   ```

2. **Set up a virtual environment**:

   ```bash
   python3 -m venv env
   ```

3. **Activate the virtual environment**:

   - On macOS/Linux:
     ```bash
     source env/bin/activate
     ```
   - On Windows:
     ```bash
     .\env\Scripts\activate
     ```

4. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

## Requirements

- Python 3.13 or higher
- PostgreSQL (for database)
- Railway.app (for deployment)

### Libraries:

- `Django` - Web framework for building the backend
- `dj-database-url` - Parse database URL for Django configurations
- `psycopg2` - PostgreSQL adapter for Python
- `python-dotenv` - Manage environment variables

## Setup

Before running the backend, you need to set up the environment variables in a `.env` file.

### Environment Variables

The backend requires the following environment variables:

- `DJANGO_SECRET_KEY`: A secret key for Django (You can generate this using Django's `django.core.management.utils.get_random_secret_key()`).
- `DATABASE_URL`: The URL of the PostgreSQL database (provided by Railway or any PostgreSQL host).

Example `.env` file:

```env
DJANGO_SECRET_KEY=your-secret-key
DATABASE_URL=postgres://user:password@postgres.railway.internal:5432/database_name
```

### Running the Project

1. **Apply migrations**:

After setting up the database and environment variables, run the migrations to set up your database schema:

```bash
  python manage.py migrate
```

2. **Run the development server**:

To start the backend locally, use the following command:

```bash
  python manage.py runserver
```

3. **Run the development server**:

To start the backend locally, use the following command:

```bash
  python manage.py runserver
```

### Deployment

The backend is deployed on Railway.app. Ensure that your DATABASE_URL is set correctly in the Railway environment variables. Railway will handle the deployment automatically when you push to the main branch.

To deploy:

    1. Commit your changes to GitHub.

    2. Push the changes to the Railway environment (it will automatically deploy).

### Usage

Once the backend is running, you can interact with it by sending API requests to the following endpoints (add more based on your project):

`GET /api/v1/trips/`: Get a list of trips.

`POST /api/v1/trips/`: Create a new trip.

`GET /api/v1/trips/{id}/`: Get details of a specific trip.

`PUT /api/v1/trips/{id}/`: Update a trip.

### Troubleshooting

If you encounter errors during migration or when starting the server, ensure that:

    1. The `DATABASE_URL` is correctly set in the .env file.

    2. Your database is running and accessible.

    3. Any missing dependencies are installed by running `pip install -r requirements.txt`.

If you are getting errors related to `ModuleNotFoundError: No module named 'dotenv'`, ensure that python-dotenv is correctly installed and listed in your requirements.txt.
