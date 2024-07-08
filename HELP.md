# Spring Boot Bank Application

This project is a simple Spring Boot application that simulates basic bank functionalities such as managing customers, accounts, transactions, and related operations. The application provides RESTful endpoints to perform these operations.

## Project Structure

### Controllers

- **CustomerController**: Manages customer-related operations.
    - `createCustomer()`: Create a new customer.
    - `getCustomerById()`: Retrieve customer details by ID.
    - `getBalance()`: Check the balance of a customer's account.
    - `getLastFiveTransactions()`: Get the last five transactions of a customer.
    - `transferMoney()`: Transfer money from one customer's account to another.

- **TransactionController**: Manages transaction-related operations.
    - `recordTransaction()`: Record a new transaction.
    - `getAllTransactions()`: Retrieve all transactions.

### Services

- **CustomerService**: Handles operations related to customers.
    - `createCustomer()`: Create a new customer.
    - `getCustomerById()`: Retrieve customer details by ID.
    - `checkBalance()`: Check the balance of a customer's account.
    - `getLastFiveTransactions()`: Get the last five transactions of a customer.
    - `transferMoney()`: Transfer money between customers.

- **TransactionService**: Handles operations related to transactions.
    - `recordTransaction()`: Record a new transaction.
    - `getAllTransactions()`: Retrieve all transactions.

### Domain Models

- **Customer**: Represents a customer with a savings account.
    - `Long customerId`
    - `String name`
    - `SavingsAccount savingsAccount`

- **SavingsAccount**: Represents a customer's savings account.
    - `Long accountId`
    - `double balance`

- **Transaction**: Represents a transaction between accounts.
    - `Long transactionId`
    - `double amount`
    - `Long fromAccountId`
    - `Long toAccountId`
    - `LocalDateTime timestamp`

## Setting Up the Project in IntelliJ IDEA

### Prerequisites

1. **Install IntelliJ IDEA**: [Download IntelliJ IDEA](https://www.jetbrains.com/idea/download/)
2. **Java Development Kit (JDK)**: [Download JDK](https://adoptopenjdk.net/)

### Steps to Set Up

1. **Create a New Project**
    - Open IntelliJ IDEA.
    - Click on `File` > `New` > `Project`.
    - Select `Spring Initializr` and configure your project with the necessary dependencies (`Spring Web`, `Spring Boot DevTools`).

2. **Implement the Domain Models**
    - Create `Customer` and `SavingsAccount` classes in the `com.example` package.
    - Define constructors, getters, and setters for each class.

3. **Implement Service Classes**
    - Create `CustomerService` and `TransactionService` classes.
    - Implement business logic methods for customer and transaction operations.

4. **Implement Controller Classes**
    - Create `CustomerController` and `TransactionController` classes.
    - Define RESTful endpoints to handle HTTP requests.

5. **Run Your Application**
    - Navigate to the main application class (e.g., `Application.java`).
    - Right-click on the class and select `Run 'Application'`.
    - Use a web browser or tools like Postman to test your endpoints.

## Diagram

Below is a high-level diagram representing the structure and flow of the Spring Boot project:

```plaintext
+-----------------------------------------------+
|                Spring Boot Bank               |
|                   Application                 |
+-----------------------------------------------+
               |
               |
               v
+----------------------------+      +---------------------------+
|        Controllers         |      |        Services           |
+----------------------------+      +---------------------------+
|                            |      |                           |
| CustomerController         |<---->| CustomerService           |
| - createCustomer()         |      | - createCustomer()        |
| - getCustomerById()        |      | - getCustomerById()       |
| - getBalance()             |      | - checkBalance()          |
| - getLastFiveTransactions()|      | - getLastFiveTransactions()|
| - transferMoney()          |      | - transferMoney()         |
|                            |      |                           |
| TransactionController      |<---->| TransactionService        |
| - recordTransaction()      |      | - recordTransaction()     |
| - getAllTransactions()     |      | - getAllTransactions()    |
|                            |      |                           |
+----------------------------+      +---------------------------+
               |
               |
               v
+-----------------------------------------------+
|                  Domain Models                |
+-----------------------------------------------+
|                                               |
| Customer                                      |
| - Long customerId                             |
| - String name                                 |
| - SavingsAccount savingsAccount               |
|                                               |
| SavingsAccount                                |
| - Long accountId                              |
| - double balance                              |
|                                               |
| Transaction                                   |
| - Long transactionId                          |
| - double amount                               |
| - Long fromAccountId                          |
| - Long toAccountId                            |
| - LocalDateTime timestamp                     |
|                                               |
+-----------------------------------------------+
