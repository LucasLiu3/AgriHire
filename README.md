# AgriHire – Agricultural Equipment Hire Management System

AgriHire is a full-stack web application designed to manage agricultural equipment hire across multiple store locations.

The system provides customers with an online platform to browse agricultural equipment, manage a shopping cart, make bookings and payments, and review their hire history. It also provides dedicated workflows for staff and different levels of management to manage equipment, inventory, customers, bookings, promotions, and operational reporting.

## Tech Stack

### Backend
- Python
- Flask
- MySQL
- Jinja2

### Frontend
- HTML5
- CSS3
- JavaScript
- Bootstrap

### Other
- Git
- Werkzeug password hashing
- Flask session management

## Key Features

### Customer

Customers can:

- Register and log in to the system
- Browse agricultural equipment
- Search and view equipment details
- Select equipment hire dates
- Add equipment to a shopping cart
- Create equipment bookings
- Make payments
- View booking history and receipts
- Manage their profile
- Submit feedback
- Submit equipment requests and reports

### Equipment Hire & Booking

The booking workflow supports:

1. Equipment discovery
2. Equipment detail and availability checking
3. Hire date selection
4. Shopping cart management
5. Hire period and price calculation
6. Booking creation
7. Payment processing
8. Booking records and receipts

Existing bookings are checked when displaying equipment availability to help prevent conflicts during the selected hire period.

### Staff & Management

The application provides different workflows for:

- Staff
- Local Managers
- National Managers
- System Administrators

Depending on their role, users can manage:

- Equipment
- Inventory
- Bookings
- Customers
- Staff
- Customer verification
- Equipment requests
- Equipment reports
- Promotions
- News
- Feedback

### Management Reporting

Management dashboards provide operational information including:

- Monthly revenue
- Equipment booking activity
- Popular equipment
- Long-duration bookings
- Equipment and inventory status
- Equipment status distribution

## Authentication & User Management

AgriHire implements account authentication and role-based workflows.

Authentication features include:

- User registration
- Username and email validation
- Password complexity validation
- Secure password hashing
- Login authentication
- Flask session management
- Account status checking
- Role-based dashboard redirection
- Customer identification document upload

The system supports five main user roles:

| Role | Main Responsibility |
|---|---|
| Customer | Browse and hire agricultural equipment |
| Staff | Support day-to-day store operations |
| Local Manager | Manage local store operations |
| National Manager | Monitor and manage operations across stores |
| System Administrator | Manage system-level data and administration |

## Database Design

AgriHire uses a relational MySQL database to manage the application's business data.

The database contains more than 20 related tables covering areas such as:

- Accounts
- Customers
- Staff
- Management
- Stores
- Equipment categories
- Equipment
- Inventory
- Shopping carts
- Bookings
- Booking details
- Payments
- Equipment pickup and return records
- Service records
- Promotions
- News
- Notifications
- Messages
- Feedback
- Customer equipment requests
- Customer equipment reports

Primary keys, foreign keys, unique constraints and cascading relationships are used to maintain data integrity.

A simplified core data flow is:

```text
Customer
   |
   v
Shopping Cart
   |
   v
Booking
   |
   +---- Booking Details ---- Equipment
   |
   v
Payment
   |
   v
Pickup / Return Records
```

Store operations are organised around:

```text
Store
  |
  +-- Staff
  +-- Equipment
  +-- Inventory
  +-- Bookings
  +-- Promotions
  +-- News
```

## Project Structure

```text
AgriHire/
|
|-- app/
|   |-- authentication.py
|   |-- customer_view.py
|   |-- staff_view.py
|   |-- local_view.py
|   |-- national_view.py
|   |-- admin_view.py
|   `-- ...
|
|-- templates/
|   |-- customer/
|   |-- staff/
|   |-- local/
|   |-- national/
|   |-- admin/
|   `-- ...
|
|-- static/
|   |-- css/
|   |-- js/
|   `-- images/
|
|-- AgriHireDB.sql
|-- connect.py
|-- run.py
`-- README.md
```

## Getting Started

### Prerequisites

Make sure the following are installed:

- Python
- MySQL
- pip

### 1. Clone the repository

```bash
git clone <repository-url>
cd AgriHire
```

### 2. Create a virtual environment

Windows:

```bash
python -m venv venv
venv\Scripts\activate
```

macOS/Linux:

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Create the database

Create a MySQL database and import:

```text
AgriHireDB.sql
```

### 5. Configure the database connection

Configure the required MySQL connection details for the application.

> For security, database credentials and Flask secret keys should be stored using environment variables and should not be committed to source control.

### 6. Run the application

```bash
python run.py
```

Open the local Flask address shown in the terminal in your browser.

## What I Learned

This project gave me practical experience building a database-driven full-stack web application and implementing business workflows beyond basic CRUD operations.

Through AgriHire, I gained experience with:

- Building web applications using Flask
- Designing relational databases with MySQL
- Writing SQL queries involving multiple related tables
- Implementing authentication and session management
- Hashing and validating user passwords
- Designing workflows for multiple user roles
- Implementing booking and inventory business logic
- Connecting frontend forms and views with backend functionality
- Building management dashboards and reports
- Structuring a larger web application across multiple functional modules

## Future Improvements

Potential improvements include:

- Move database credentials and secret keys to environment variables
- Introduce a dedicated data access/service layer
- Refactor large route modules into smaller components
- Add automated unit and integration tests
- Improve authorization checks using reusable decorators or middleware
- Add database migrations
- Improve form validation and error handling
- Add API endpoints for selected functionality
- Containerise the application using Docker
- Add CI/CD automation
- Deploy the application to a cloud platform

## About the Project

AgriHire was developed as a full-stack software development project focused on applying Python, Flask, MySQL and web development concepts to a realistic agricultural equipment hire scenario.

The project demonstrates database design, authentication, multi-role workflows, booking and inventory management, and management reporting within a single web application.
