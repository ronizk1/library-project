# Library Management System

Welcome to the Library Management System! This Flask application allows users to manage a library, including registering users, adding books, loaning and returning books, and more.

## Table of Contents

- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
  - [Register](#register)
  - [Login](#login)
  - [Add Book](#add-book)
  - [Loan Book](#loan-book)
  - [Return Book](#return-book)
  - [Protected Routes](#protected-routes)
- [API Endpoints](#api-endpoints)
- [Database Models](#database-models)
- [Late Loans](#late-loans)
- [All Loans](#all-loans)
- [All Books](#all-books)
- [All Customers](#all-Customers)
- [Contributing](#contributing)
- [License](#license)

## Getting Started

### Prerequisites

- Python 3.x
- Flask
- Other dependencies (specified in `requirements.txt`)

### Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/your-username/library-management-system.git
    ```

2. Navigate to the project directory:

    ```bash
    cd library-management-system
    ```

3. Install dependencies:

    ```bash
    pip install -r requirements.txt
    ```

4. Set up the database:

    ```bash
    python app.py
    ```

## Usage

### Register

To register a new user, make a POST request to `/register` with the user details:

```bash
curl -X POST -H "Content-Type: application/json" -d '{"username":"example", "password":"password", "name":"John Doe", "city":"City", "age":25}' http://localhost:5000/register



Certainly! Here's a comprehensive README.md file for your Flask project:

markdown
Copy code
# Library Management System

Welcome to the Library Management System! This Flask application allows users to manage a library, including registering users, adding books, loaning and returning books, and more.

## Table of Contents

- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
  - [Register](#register)
  - [Login](#login)
  - [Add Book](#add-book)
  - [Loan Book](#loan-book)
  - [Return Book](#return-book)
  - [Protected Routes](#protected-routes)
- [API Endpoints](#api-endpoints)
- [Database Models](#database-models)
- [Late Loans](#late-loans)
- [Contributing](#contributing)
- [License](#license)

## Getting Started

### Prerequisites

- Python 3.x
- Flask
- Other dependencies (specified in `requirements.txt`)

### Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/your-username/library-management-system.git
    ```

2. Navigate to the project directory:

    ```bash
    cd library-management-system
    ```

3. Install dependencies:

    ```bash
    pip install -r requirements.txt
    ```

4. Set up the database:

    ```bash
    python app.py
    ```

## Usage

### Register

To register a new user, make a POST request to `/register` with the user details:

```bash
curl -X POST -H "Content-Type: application/json" -d '{"username":"example", "password":"password", "name":"John Doe", "city":"City", "age":25}' http://localhost:5000/register
Login
To log in and obtain an access token, make a POST request to /login with the user credentials:

bash
Copy code
curl -X POST -H "Content-Type: application/json" -d '{"username":"example", "password":"password"}' http://localhost:5000/login
Add Book
To add a new book, make a POST request to /add_book with the book details:

bash
Copy code
curl -X POST -H "Content-Type: application/json" -H "Authorization: Bearer YOUR_ACCESS_TOKEN" -d '{"name":"Book Name", "author":"Author", "year_published":2022, "book_type":1}' http://localhost:5000/add_book
Loan Book
To loan a book, make a POST request to /loan_book with the book ID:

bash
Copy code
curl -X POST -H "Content-Type: application/json" -H "Authorization: Bearer YOUR_ACCESS_TOKEN" -d '{"book_id":1}' http://localhost:5000/loan_book
Return Book
To return a book, make a POST request to /return_book with the book ID:

bash
Copy code
curl -X POST -H "Content-Type: application/json" -H "Authorization: Bearer YOUR_ACCESS_TOKEN" -d '{"book_id_return":1}' http://localhost:5000/return_book
Protected Routes
To access protected routes, include the access token in the request to /protected:

bash
Copy code
curl -H "Authorization: Bearer YOUR_ACCESS_TOKEN" http://localhost:5000/protected
API Endpoints
/register - Register a new user.
/login - Log in a user and obtain an access token.
/add_book - Add a new book to the system.
/loan_book - Loan a book.
/return_book - Return a book.
/protected - Protected route, requires a valid access token.
/all_books - Get information about all books.
/loans - Get information about loans.
/late_loans - Get information about late loans.
/customers - Get information about all customers.
/books - Get information about all books.
/find_book - Find information about a specific book.
/find_customer - Find information about a specific customer.

Database Models
Customer
id (Integer, Primary Key)
name (String, Not Null)
city (String, Not Null)
age (Integer, Not Null)
username (String, Unique, Not Null)
password (String, Not Null)
loans (Relationship with Loan)
Book
id (Integer, Primary Key)
name (String, Not Null)
author (String, Not Null)
year_published (Integer, Not Null)
book_type (Integer, Not Null)
loans (Relationship with Loan)
Loan
cust_id (Integer, Foreign Key, Primary Key)
book_id (Integer, Foreign Key, Primary Key)
loan_date (DateTime, Not Null, Default: Current UTC Time)
return_date (DateTime, Nullable)