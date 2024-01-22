# Flask Library Management System

This is a simple Library Management System built using Flask, SQLAlchemy, Flask-JWT-Extended, and Bootstrap. The system allows users to register, log in, borrow and return books, and provides administrative functionality.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)

## Features

- **User Registration**: Users can register with the system, providing necessary information such as username, password, name, city, age, and role (with default role as 'user').
- **User Authentication**: Secure user authentication using JWT tokens. Passwords are hashed and salted for security.
- **Book Operations**: Users and admins can perform various operations on books, including adding, viewing, and searching for books.
- **Borrow and Return**: Users can borrow and return books. Due date tracking is implemented to manage book returns.
- **Admin Functionality**: Admins have additional privileges, including adding books and viewing all loans. Admins are identified by their 'admin' role.


## Usage
Usage
- Register a User:

Use the /register endpoint to register a new user by providing necessary details.
- Log In:

Use the /login endpoint to log in with your credentials and receive a JWT token.
Book Operations:

Use /add_book to add new books (admin only).
Use /all_books to get a list of all available books.
- Borrow and Return:

Use /loan_book to borrow a book.
Use /return_book to return a borrowed book.
- Admin Actions:

Admins can use /loans to view all loans.
Admins can use /late_loans to view late loans.
Admins can use /customers to view all customers.
Admins can use /books to view all books.
- Search Functionality:

Use /find_book to find a book by name.
Use /find_customer to find a customer by name.
- User-Specific Actions:

Users can use /user_loans to view all loans for the current user.
- Protected Route:

Access the protected route /protected to get information about the current user (requires authentication).
- Find by ID:

Use /find_book_by_id/{book_id} to find a book by its ID.
Use /find_customer_by_id/{customer_id} to find a customer by their ID.


## API Endpoints

- POST /register: Register a new user. Requires providing username, password, name, city, age, and an optional role (default is 'user').
- POST /login: Log in with existing credentials. Returns a JWT token for authentication.
- POST /add_book: Add a new book (admin only). Requires providing name, author, year_published, and book_type.
- POST /loan_book: Loan a book. Requires providing the book_id.
- GET /all_books: Get all available books.
- GET /loans: View all loans (admin only).
- POST /return_book: Return a book. Requires providing the book_id_return.
- GET /late_loans: View late loans (admin only).
- GET /customers: View all customers (admin only).
- GET /books: View all books.
- POST /find_book: Find a book by name. Requires providing the book_name.
- POST /find_customer: Find a customer by name. Requires providing the customer_name.
- GET /user_loans: Get all loans for the current user.

## Role System
- Users are assigned roles ('user' by default).
- Admins have additional privileges, including adding books and viewing all loans.
- Role-based access control is implemented to restrict certain operations to admins only.

## Installation

1. Clone the repository:

```bash
git clone https://github.com/your-username/flask-library-management.git
cd flask-library-management


