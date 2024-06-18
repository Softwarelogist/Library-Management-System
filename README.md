# Library Management System

## Overview

The Library Management System is a JavaFX application designed to help libraries manage their operations efficiently. This system allows librarians to register patrons, manage book inventory, and handle book issuance and returns. It is built using Java and JavaFX for the frontend and MySQL for the backend database.

## Features

- **Patron Registration:** Easily register new patrons with their name and email.
- **Book Management:** Add, issue, and return books with a few clicks.
- **User-Friendly Interface:** Intuitive and visually appealing GUI.
- **Database Integration:** Uses MySQL for reliable and efficient data storage.

## Requirements

### Software

1. **Java Development Kit (JDK) 11 or higher**
    - [Download JDK](https://www.oracle.com/java/technologies/javase-downloads.html)
2. **MySQL Database**
    - [Download MySQL](https://dev.mysql.com/downloads/installer/)
3. **Apache Maven**
    - [Download Maven](https://maven.apache.org/download.cgi)
4. **MySQL Connector for Java**
    - [Download MySQL Connector](https://dev.mysql.com/downloads/connector/j/)

### Hardware

- A computer with at least 2GB of RAM.
- At least 500MB of free disk space.

## Installation

### Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/library-management-system.git
cd library-management-system

## Step 2: Set Up the MySQL Database
# 1 Install MySQL:
Follow the installation guide on the MySQL website to install MySQL on your system.
# 2 Create a Database:
Open the MySQL command line client and run the following command to create a database:
CREATE DATABASE library_management

# 3 Create Tables:

Use the following SQL script to create the necessary tables:
USE library_management;

CREATE TABLE patrons (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL
);

CREATE TABLE books (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    author VARCHAR(255) NOT NULL,
    publisher VARCHAR(255),
    year_published INT
);

CREATE TABLE transactions (
    id INT AUTO_INCREMENT PRIMARY KEY,
    book_id INT,
    patron_id INT,
    issue_date DATE,
    return_date DATE,
    FOREIGN KEY (book_id) REFERENCES books(id),
    FOREIGN KEY (patron_id) REFERENCES patrons(id)
);
tep 3: Configure Database Connection
Download MySQL Connector for Java:

Download the MySQL Connector/J from the official MySQL website.
Add MySQL Connector to Project:

Add the MySQL Connector JAR file to your project's lib directory.
Update Database Configuration:

Open DatabaseHelper.java and update the database connection details:
java
Copy code
public class DatabaseHelper {
    private static final String URL = "jdbc:mysql://localhost:3306/library_management";
    private static final String USER = "your-username";
    private static final String PASSWORD = "your-password";

    public static Connection connect() throws SQLException {
        return DriverManager.getConnection(URL, USER, PASSWORD);
    }
}
## Step 4: Build the Project
# Use Maven to build the project:
mvn clean install
## Step 5: Run the Application
Run the application using the following Maven command:
mvn javafx:run

# Usage
# Login: Use the login screen to access the main dashboard.
# Register Patron: Navigate to the patron registration section and enter the required details.
# Manage Books: Use the options to add new books, issue books to patrons, and process book returns.
# Screenshots
# Sign up
![image](https://github.com/Softwarelogist/Library-Management-System/assets/83673608/34d9d75b-5f96-4390-b1a2-8015304bc800)
# Sing in
![image](https://github.com/Softwarelogist/Library-Management-System/assets/83673608/d8e4c631-6b6e-48a1-a5a3-976df6a131e7)
# Add Book
![image](https://github.com/Softwarelogist/Library-Management-System/assets/83673608/261a7c10-5734-4994-9902-2a82cc4e0c8d)
# Issue Book
![image](https://github.com/Softwarelogist/Library-Management-System/assets/83673608/3aa3383f-5874-4431-a999-50b977cb49f1)
# Return Book
![image](https://github.com/Softwarelogist/Library-Management-System/assets/83673608/d13646bd-2a87-432e-bd36-8cef92f2ac87)
# Register Patron
![image](https://github.com/Softwarelogist/Library-Management-System/assets/83673608/07a6a5e9-a193-4f69-91b7-0d6da665b7f1)

# Contributing
We welcome contributions! Please fork the repository and submit a pull request for review.

# License
This project is licensed under the MIT License. See the LICENSE file for more details.

% Contact
For any inquiries or support, please contact us at arshadsaeed2709@gmail.com








