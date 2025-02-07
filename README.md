# Flask Shopping List

## Description

Flask Shopping List is a simple REST API that allows users to manage their shopping lists efficiently. Users can create, read, update, and delete shopping lists and items within them. The project is built using Flask, Flask-SQLAlchemy, and Flask-RESTful.

## Features

- User authentication (JWT-based)
- CRUD operations for shopping lists
- CRUD operations for shopping list items
- SQLite/PostgreSQL support
- API documentation using Swagger (Flask-Swagger-UI)

## Technologies Used

- Python 3
- Flask
- Flask-SQLAlchemy
- Flask-RESTful
- Flask-JWT-Extended
- Flask-Migrate
- Flask-Swagger-UI

## Installation

### 1. Clone the repository

```sh
git clone https://github.com/yourusername/flask_shopping_list.git
cd flask_shopping_list
```

### 2. Create a virtual environment and activate it

```sh
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```

### 3. Install dependencies

```sh
pip install -r requirements.txt
```

### 4. Set up environment variables

Create a `.env` file in the root directory and define:

```ini
FLASK_APP=app.py
FLASK_ENV=development
SECRET_KEY=your_secret_key
DATABASE_URL=sqlite:///shopping_list.db  # Change for PostgreSQL
```

### 5. Run database migrations

```sh
flask db init
flask db migrate -m "Initial migration."
flask db upgrade
```

### 6. Start the application

```sh
flask run
```

The API will be available at `http://127.0.0.1:5000/`.

## API Endpoints

### Authentication

- `POST /auth/register` - Register a new user
- `POST /auth/login` - Log in and receive a JWT token

### Shopping Lists

- `GET /shopping-lists` - Retrieve all shopping lists
- `POST /shopping-lists` - Create a new shopping list
- `GET /shopping-lists/<id>` - Get a specific shopping list
- `PUT /shopping-lists/<id>` - Update a shopping list
- `DELETE /shopping-lists/<id>` - Delete a shopping list

### Shopping List Items

- `POST /shopping-lists/<list_id>/items` - Add an item to a shopping list
- `GET /shopping-lists/<list_id>/items` - Retrieve items from a shopping list
- `PUT /shopping-lists/<list_id>/items/<item_id>` - Update an item
- `DELETE /shopping-lists/<list_id>/items/<item_id>` - Remove an item

## Future Improvements

- User roles and permissions
- Support for multiple users per list (shared lists)
- Docker containerization
- Redis caching for improved performance

## License

This project is licensed under the MIT License.

