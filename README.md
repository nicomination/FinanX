# FinanX: The Rise of the Ledger

**FinanX** is a modern web application designed for managing personal finances. It provides a comprehensive solution for tracking income, expenses, and stock analysis using AI. The system consists of multiple interconnected repositories, each responsible for different functionalities. This documentation provides an overview of the project, the technologies used, and a guide on how to use it.

---

## Technologies

- **Frontend**: Angular
  - Angular Universal for SSR (Server-Side Rendering)
  - Using Chart.js or similar libraries for charts (e.g., financial statistics)
  - Forms and State Management for the financial dashboard

- **Backend**: FastAPI
  - RESTful APIs for financial data and AI-powered analysis
  - SQLAlchemy for database access
  - TensorFlow / scikit-learn for AI-based stock analysis

- **Database**: PostgreSQL
  - Storage for user, financial, and category data

- **AI**: Python
  - TensorFlow or scikit-learn for stock analysis and predictions

- **Nginx**:
  - Reverse Proxy for Angular frontend and FastAPI backends

- **Docker and Docker Compose**:
  - Containerization and orchestration of the entire application

---

## Features

1. **User Registration and Authentication**
   - Register with email and password
   - Login/Logout
   - Password reset
   - User session management with JWT

2. **Dashboard (Financial Overview)**
   - Display income, expenses, and account balance
   - Show charts for monthly overview and categorization

3. **Manage Income and Expenses**
   - Add, edit, and delete income and expenses
   - Assign categories (e.g., “Food”, “Rent”)
   - Display monthly and yearly reports

4. **Financial Statistics and Insights**
   - Calculate and display monthly income and expenses
   - Categorized expense analysis (e.g., how much spent on "Food" or "Leisure")
   - Forecasts for upcoming months

5. **AI-Powered Stock Analysis**
   - Fetch real-time stock prices
   - Provide analyses and recommendations (e.g., whether to "buy" or "sell" a stock)

6. **Categorization and Budgeting**
   - Create categories and budget goals
   - Notifications when the budget is exceeded

7. **PGAdmin (Database Management)**
   - Manage PostgreSQL database
   - Backup and optimize the database

8. **Database Modeling**
   - Store user, income, expense, category, and budget data

9. **Nginx as Reverse Proxy**
   - Route requests to different services (Frontend, APIs, PGAdmin)
   - Optimize traffic and caching

10. **Docker and Docker Compose**
   - Containerize the application for easy deployment and scaling

---

## Project Overview

```bash
+---------------------------------------------------------+
|                    Nginx Reverse Proxy                |
|   - Routes requests to Angular, API Backend, PGAdmin   |
+--------------------------+------------------------------+
                           |
        +------------------+---------------------------+
        |                                      |
+-------v-------+                        +---------v---------+
|   Angular     |                        | FastAPI Backend 1 |
|   Frontend    |  <----->  API (JSON)   | (Finance)         |
|               |                        +-------------------+
+---------------+
        |
+-------v-----------------+
| FastAPI Backend 2 (KI)  |
| (Stockanalysis)         |
+-------------------------+

            +------------------------------+
            |      PostgreSQL Database     |
            |   - User, Transactions       |
            |   - Categories, Budgets      |
            +------------------------------+

            +-------------------------+
            |     PGAdmin UI          |
            |   (Databasemanagement)  |
            +-------------------------+
```

---

## How to Use the FinanX System

### 1. Clone the Repository

To run the **FinanX** project locally, clone the main repository and initialize the submodules:

```bash
git clone https://github.com/nicomination/FinanX.git FinanX
cd FinanX
git submodule init
git submodule update
docker compose up -d --build
```

---

## Project Structure

```bash
FinanX/
├── .env                   # Environment variables file
├── .gitignore             # Git ignore file
├── .gitmodules            # Git submodule configuration
├── LICENSE                # License file
├── README.md              # Project documentation
├── docker-compose.yml     # Docker Compose configuration file
├── J4arv15.nginx/         # Nginx reverse proxy configuration
├── J4arv15.dashboard/     # Angular frontend repository
├── J4arv15.finance-api/   # FastAPI backend for finance management
└── J4arv15.stock-api/     # FastAPI backend for AI-based stock analysis
```
---

## Development and Contributions

If you want to contribute to the development of FinanX, feel free to fork the repository and submit pull requests. Please follow these steps:

1. **Fork** the repository.
2. Create a **new branch** for your changes.
3. Submit a **pull request** to the main development line.
4. Ensure all **tests** pass and the code is properly formatted.

---

## Aditional Information

- **Documentation**: For further details on individual services and APIs, refer to the respective submodules.
- **License**: This project is licensed under the MIT License. See the LICENSE file for more details.