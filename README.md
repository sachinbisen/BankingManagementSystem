# 💳 Banking Management System

This Java-based banking application simulates core banking functionalities including user registration, account management, and transaction handling. The project uses **Java AWT for GUI**, **JDBC for database interaction**, and **MySQL** for data storage — making it a solid demonstration of integrating Java with SQL databases.

---

## 🚀 Features

### 1. 👤 User Management
- **Registration**  
  Users can register by providing their full name, email, and password.  
  The system ensures:
  - Email uniqueness  
  - Secure storage of user credentials

- **Login**  
  Registered users can log in using their email and password to access account-related features.

---

### 2. 🏦 Account Management
- **Open Account**  
  Users can open a bank account after login by entering:
  - Initial deposit amount
  - Security PIN

- **Check Balance**  
  Users can view their current account balance by entering:
  - Account number
  - Security PIN

---

### 3. 💰 Transaction Handling
- **Credit Money**  
  Deposit funds into a user's account after authentication.

- **Debit Money**  
  Withdraw funds from the account (only if balance is sufficient).

- **Transfer Money**  
  Transfer funds to another account in the system by entering:
  - Receiver’s account number
  - Amount
  - Security PIN

---

### 4. 🗃️ Database Interaction
- Utilizes **MySQL** to manage:
  - User information
  - Account details
  - Transactional updates
- JDBC handles all operations with proper connection and transaction management to maintain **data integrity**.

---

## ⚙️ Setup Instructions

### ✅ Prerequisites
- Java JDK (Java 8+)
- MySQL Server
- MySQL JDBC Driver (e.g., `mysql-connector-java-8.x.xx.jar`)

---

### 🏗️ Database Setup

Run the following SQL script in your MySQL terminal or GUI:

```sql
CREATE DATABASE bank;
USE bank;

CREATE TABLE User (
    id INT AUTO_INCREMENT PRIMARY KEY,
    full_name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    password VARCHAR(100) NOT NULL
);

CREATE TABLE Accounts (
    id INT AUTO_INCREMENT PRIMARY KEY,
    account_number BIGINT NOT NULL UNIQUE,
    full_name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL,
    balance DOUBLE NOT NULL,
    security_pin VARCHAR(10) NOT NULL
);
