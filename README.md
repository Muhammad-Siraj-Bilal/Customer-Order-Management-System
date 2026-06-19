# Customer Order Management System

A simple customer and order management system built with **Python**, **SQLAlchemy ORM**, and **SQLite**.

The project demonstrates how to create relational database tables, define relationships between customers and orders, insert data, and retrieve records using SQLAlchemy.

## Features

* Create and manage customer records
* Create and manage customer orders
* One-to-many relationship between customers and orders
* Store data in an SQLite database
* Retrieve all customers
* Retrieve all orders
* Retrieve orders belonging to a specific customer
* Automatic database table creation using SQLAlchemy

## Technologies Used

* Python
* SQLAlchemy
* SQLite
* Object-Relational Mapping

## Database Structure

The system contains two main tables:

### Customers

| Column     | Type    | Description                |
| ---------- | ------- | -------------------------- |
| CustomerID | Integer | Unique customer identifier |
| Name       | String  | Customer name              |
| Email      | String  | Customer email address     |
| Phone      | String  | Customer phone number      |
| Address    | String  | Customer address           |

### Orders

| Column     | Type    | Description                 |
| ---------- | ------- | --------------------------- |
| OrderID    | Integer | Unique order identifier     |
| CustomerID | Integer | References the customer     |
| Product    | String  | Name of the ordered product |
| Quantity   | Integer | Number of items ordered     |
| OrderDate  | Date    | Date the order was placed   |

## Relationship

The project uses a **one-to-many relationship**:

* One customer can have multiple orders.
* Each order belongs to one customer.

```python
orders = relationship('Order', back_populates='customer')
```

```python
customer = relationship('Customer', back_populates='orders')
```

## Installation

Clone the repository:

```bash
git clone https://github.com/your-username/customer-order-management-system.git
```

Move into the project folder:

```bash
cd customer-order-management-system
```

Install SQLAlchemy:

```bash
pip install sqlalchemy
```

## Running the Project

Run the Python file:

```bash
python main.py
```

The program will automatically create the following SQLite database file:

```text
customer_orders.db
```

It will then:

1. Create the `Customers` and `Orders` tables.
2. Add sample customers.
3. Add sample orders.
4. Display all customers.
5. Display all orders.
6. Display orders belonging to a selected customer.

## Example Output

```text
Customer(CustomerID=1, Name='John Doe', Email='john@example.com', Phone='123456789', Address='123 Main St')

Customer(CustomerID=2, Name='Jane Smith', Email='jane@example.com', Phone='987654321', Address='456 Elm St')

Order(OrderID=1, CustomerID=1, Product='Widget', Quantity=5, OrderDate='2023-01-01')

Order(OrderID=2, CustomerID=1, Product='Gadget', Quantity=3, OrderDate='2023-02-15')

Order(OrderID=3, CustomerID=2, Product='Widget', Quantity=10, OrderDate='2023-03-10')
```

## Project Structure

```text
customer-order-management-system/
│
├── main.py
├── customer_orders.db
├── requirements.txt
├── .gitignore
└── README.md
```

## requirements.txt

```text
SQLAlchemy
```

## .gitignore

```text
__pycache__/
*.pyc
*.db
.env
venv/
.venv/
```

## Learning Objectives

This project demonstrates:

* Creating database models with SQLAlchemy
* Using primary keys and foreign keys
* Establishing table relationships
* Creating database sessions
* Adding and committing records
* Querying database records
* Filtering data using SQLAlchemy ORM

## Future Improvements

* Add update and delete operations
* Add input validation
* Create a command-line interface
* Add product pricing and total order value
* Add order status tracking
* Build a Flask or FastAPI web interface
* Add automated tests
* Use environment variables for database configuration

## Author

**Muhammad Danish Bin Nihal**

## License

This project is available for educational and portfolio purposes.
