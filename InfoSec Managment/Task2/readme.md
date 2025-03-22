# Flask RESTful API with JWT Authentication

## Overview
This project is a RESTful API built using Flask, providing user authentication and product management features. The API uses JWT for authentication and MySQL as the database.

## Features
- User registration and login with JWT authentication
- Secure password hashing using Bcrypt
- Token-based authentication with JWT
- Product management (CRUD operations)
- Role-based access control
- Token revocation and logout functionality

## Technologies Used
- Python
- Flask
- Flask-JWT-Extended
- Flask-SQLAlchemy
- Flask-Bcrypt
- MySQL
- dotenv (for environment variables)

## Installation

### Prerequisites
Make sure you have the following installed:
- Python 3.7+
- MySQL database
- Virtual environment (optional but recommended)

### Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo.git
   cd your-repo
   ```
2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Set up the environment variables:
   Create a `.env` file and add the following:
   ```
   SECRET_KEY=your_secret_key
   DATABASE_URI=mysql://root:@localhost/infosec
   JWT_SECRET_KEY=your_jwt_secret_key
   ```
5. Initialize the database:
   ```bash
   python
   >>> from app import db
   >>> db.create_all()
   >>> exit()
   ```
6. Run the application:
   ```bash
   python app.py
   ```
   The API will be available at `http://127.0.0.1:5000`.

## API Endpoints

### Authentication
| Method | Endpoint  | Description |
|--------|----------|-------------|
| POST   | `/signup` | Register a new user |
| POST   | `/login` | Authenticate and obtain a JWT token |
| POST   | `/logout` | Logout and revoke the JWT token |

#### Signup
![Signup](/attachments/signup.png)

#### Login
![login](/InfoSec%20Managment/Task2/attachments/login.png)

#### Logout
![logout](/attachments/logout.png)


### User Management
| Method | Endpoint  | Description |
|--------|----------|-------------|
| PUT    | `/users/<id>` | Update user details (name, password) |

![update](/attachments/update.png)

### Product Management
| Method | Endpoint  | Description |
|--------|----------|-------------|
| POST   | `/products` | Create a new product |
| GET    | `/products` | Retrieve all products (paginated) |
| GET    | `/products/<pid>` | Retrieve a specific product |
| PUT    | `/products/<pid>` | Update product details |
| DELETE | `/products/<pid>` | Delete a product |

#### Create Product
![Create](/attachments/create.png)

#### Retreive Products
![Retreive](/attachments/Retreive.png)

#### Get Product
![Get](/attachments/Get.png)

#### Update Product
![Update](/attachments/updatep.png)

#### Delete Product
![delete](/attachments/delete.png)

## JWT Authentication
- Each request requiring authentication must include the JWT token in the `Authorization` header:
  ```bash
  Authorization: Bearer your_jwt_token
  ```
  ![Auth](/attachments/Auth.png)

## Error Handling
- `404`: Resource not found
- `401`: Unauthorized or invalid token
- `500`: Internal server error

## License
This project is licensed under the MIT License.

