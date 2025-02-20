# Ecommerce API - Django REST Framework

An **E-commerce API** built using **Django REST Framework (DRF)** to handle products, orders, authentication, and more.

---

## Features
- **User Authentication** (JWT-based)
- **Product Management** (CRUD operations)
- **Order Processing**
- **Cart Functionality**
- **Stripe Payment Integration**
- **Category & Review System**
- **RESTful API Endpoints**
- **Token-based Authentication**

---

## Installation

### 1. Clone the Repository
```sh
git clone https://github.com/mayur-salokhe/ecommerce-api.git
cd ecommerce-api
```

### 2. Create Virtual Environment & Install Dependencies
```sh
python -m venv env
source env/bin/activate   # Mac/Linux
env\Scripts\activate      # Windows

pip install -r requirements.txt
```

### 3. Setup Environment Variables
Create a `.env` file in the root directory and add:
```
SECRET_KEY=your_secret_key
DEBUG=True
ALLOWED_HOSTS=*
STRIPE_SECRET_KEY=your_stripe_key
```

### 4. Run Migrations
```sh
python manage.py makemigrations
python manage.py migrate
```

### 5. Create Superuser
```sh
python manage.py createsuperuser
```

### 6. Run the Development Server
```sh
python manage.py runserver
```
API is now running at **`http://127.0.0.1:8000/`** 🎉

---

## Authentication
This API uses **JWT Authentication**.  
To get a token, send a `POST` request to:
```http
POST /api/token/
{
    "username": "your_username",
    "password": "your_password"
}
```
The response will include `access` and `refresh` tokens.  
Use the `access` token in the Authorization header:
```
Authorization: Bearer your_access_token
```

---

## API Endpoints

### Authentication
| Method | Endpoint | Description |
|--------|---------|-------------|
| `POST` | `/api/token/` | Get access & refresh tokens |
| `POST` | `/api/token/refresh/` | Refresh access token |
| `POST` | `/api/register/` | Register a new user |

### Products
| Method | Endpoint | Description |
|--------|---------|-------------|
| `GET` | `/api/products/` | List all products |
| `GET` | `/api/products/{id}/` | Retrieve a product |
| `POST` | `/api/products/` | Create a new product |
| `PUT` | `/api/products/{id}/` | Update a product |
| `DELETE` | `/api/products/{id}/` | Delete a product |

### Cart & Orders
| Method | Endpoint | Description |
|--------|---------|-------------|
| `POST` | `/api/cart/add/` | Add item to cart |
| `GET` | `/api/cart/` | View cart items |
| `POST` | `/api/orders/` | Place an order |
| `GET` | `/api/orders/` | View order history |

---

## Payment (Stripe)
To make a payment, send a `POST` request to:
```http
POST /api/checkout/
{
    "order_id": 1,
    "stripe_token": "your_stripe_token"
}
```
After successful payment, the order status updates.

---

## Running Tests
Run unit tests using:
```sh
python manage.py test
```

---

## License
This project is licensed under the **MIT License**.

---

## Contact
For any queries or contributions, feel free to reach out:  
📧 **salokhemayur9@gmail.com**  
🔗 [GitHub Profile](https://github.com/mayur-salokhe)

