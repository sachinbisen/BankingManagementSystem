Banking Application
This Java-based banking application simulates core banking functionalities, including user registration, account management, and transaction handling. The project leverages JDBC for database interaction, making it an excellent demonstration of integrating Java with SQL databases.
Features
1)User Management:
Registration: Users can register by providing their full name, email, and password. The system checks if the email already exists and stores the user information securely in the database.
Login: Registered users can log in using their email and password. Successful login grants access to account management features.
2)Account Management:
Open Account: After logging in, users who do not have an account can open a new bank account by providing their initial deposit and a security pin.
Check Balance: Users can check the balance of their bank account by entering their account number and security pin.
3)Transaction Handling:
Credit Money: Users can deposit money into their account by providing the account number and security pin.
Debit Money: Users can withdraw money from their account, provided they have sufficient balance.
Transfer Money: Users can transfer money between accounts within the system by specifying the receiver's account number, the amount, and their security pin.
4)Database Interaction:
The application uses MySQL for storing user and account data.
All transactions are handled securely with proper database transaction management, ensuring data integrity.
Setup:
Prerequisites
   1)Java JDK
   2)MySQL Database
   3)JDBC Driver for MySQL
   4)Setup MySQL Database with the following schema
//
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
//
