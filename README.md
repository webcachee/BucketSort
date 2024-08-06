# 🪣 Bucket Sort Web Application

![Screenshot 1](https://i.imgur.com/DCmPttO.png)

A full-stack web application that implements the **Bucket Sort algorithm** using **Django** and **React**. This project showcases the integration of a powerful backend built with **Django** and **Django Rest Framework (DRF)** and a dynamic frontend created with **React**.

## Features

- **Bucket Sort Algorithm**: Efficient sorting of large arrays using the Bucket Sort algorithm;
- **Array Input Methods**:
    - **Manual Input**: Users can manually enter arrays through a user-friendly interface.
    - **Random Generation**: Users can generate random arrays of specified sizes for sorting.
    - **File Upload**: Users can upload files containing arrays to be sorted.
- **Array Management**:
    - **View Arrays**: Users can view all arrays stored in the database.
    - **Edit Arrays**: Users can edit individual arrays directly from the application.
- **Interactive UI**: A clean and responsive user interface built with React and Bootstrap for a seamless user experience.

## Tech Stack

- Django
- DRF
- React
- Bootstrap
- Docker
- PostgreSQL
- SQLite
- Nginx
- pytest-django

## How to Launch
### Using Docker:

To quickly set up and launch the application using **Docker**, run:

`$ docker-compose -f docker-compose.dev.yml up --build -d`

This will build and start necessary containers for both the **Django** backend and **React** frontend.

### Manual Setup

If you prefer to set up the application manually without **Docker**, follow the steps below for both the **Django** backend and the **React** frontend.

#### Django Backend:

1. Create a virtual environment:

`$ python3 -m venv .venv`

2. Activate the virtual environment:

`$ source .venv/bin/activate`

3. Install dependencies:

`$ pip install -r requirements.txt`

4. Apply migrations:

`$ python manage.py migrate`

5. Start the Django development server:

`$ python manage.py runserver`

The API will be available at **localhost:8000/api/**.

#### React:

1. Navigate to the React project directory and install dependencies:

`$ yarn install`

2. Start the React development server:

`$ yarn start`

The application will be available at **localhost:3000**.

## Tests

The task includes implementation of tests to work with the database:

- Adding 100, 1000, 10000 random arrays;
- Fetching and sorting 100, 1000, 10000 random arrays;
- Deleting 100, 1000, 10000 random arrays;

**pytest-django** was used for writing the tests.

**Running Tests (inside the Django project directory):**

`$ pytest`

**Sample Test Results:**

![Sample Test Results](https://i.imgur.com/aa6yzJT.png)

## Environment Variables

Environment variables are specified inside the **docker-compose** file. For non-Docker local development or when customizing the environment, create a **.env** file with the following values:

```
DJANGO_SECRET_KEY=secret_key
REACT_APP_API_URL=domain.com

[POSTGRESQL // OPTIONAL]
DJANGO_DB_HOST=postgres
DJANGO_DB_NAME=postgres
DJANGO_DB_USER=postgres
DJANGO_DB_PASSWORD=postgres
DJANGO_DB_PORT=5432
```

Note that **SQLite** is used by default for non-Docker local development. To use **PostgreSQL**, specify the necessary variables in the .env file.

Generate **DJANGO_SECRET_KEY**:

`$ openssl rand -hex32`
