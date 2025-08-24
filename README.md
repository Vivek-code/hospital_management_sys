Hospital Management System 🏥
Project Overview
This is a console-based Hospital Management System developed in Java, designed to streamline the process of managing patient records, doctor information, and appointments within a hospital setting. It demonstrates foundational skills in Java programming, object-oriented design, and database integration using JDBC with MySQL.

Features
Patient Management:

Add new patient records with details such as ID, name, age, and gender.

View a list of all registered patients.

Doctor Management:

View a list of all available doctors, including their IDs and specializations.

Appointment Scheduling:

Book appointments for patients with specific doctors on a given date.

Includes validation to ensure the patient and doctor exist, and the doctor is available.

Console-Based Interface:

An interactive menu-driven interface for easy navigation and interaction.

Technologies Used
Programming Language: Java

Database: MySQL

Database Connectivity: JDBC (Java Database Connectivity)

Development Environment: IntelliJ IDEA (or any Java IDE)

Setup and Installation
To get this project up and running on your local machine, follow these steps:

1. Prerequisites
Java Development Kit (JDK) 8 or higher installed.

MySQL Server installed and running.

A Java IDE (e.g., IntelliJ IDEA, Eclipse) for development.

2. Database Setup
Create the Database:

CREATE DATABASE hospital_db;
USE hospital_db;

Create Tables:

CREATE TABLE patients (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    age INT NOT NULL,
    gender VARCHAR(10) NOT NULL
);

CREATE TABLE doctors (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    specialization VARCHAR(100) NOT NULL
);

CREATE TABLE appointments (
    id INT PRIMARY KEY AUTO_INCREMENT,
    patient_id INT,
    doctor_id INT,
    appointment_date DATE NOT NULL,
    FOREIGN KEY (patient_id) REFERENCES patients(id),
    FOREIGN KEY (doctor_id) REFERENCES doctors(id)
);

Insert Sample Data (Optional):

INSERT INTO doctors (name, specialization) VALUES ('Dr. Smith', 'Cardiology');
INSERT INTO doctors (name, specialization) VALUES ('Dr. Jones', 'Pediatrics');
INSERT INTO doctors (name, specialization) VALUES ('Dr. Lee', 'Neurology');

3. Project Configuration
Clone the Repository:

git clone https://github.com/your-username/hospital-management-system.git
cd hospital-management-system

(Replace your-username with your actual GitHub username)

Open in IDE: Import the project into your preferred Java IDE.

Update Database Credentials:

Locate the HospitalManagementSystem.java file (or a similar configuration file if created).

Update the DB_URL, DB_USER, and DB_PASSWORD variables to match your MySQL database configuration.

private static final String DB_URL = "jdbc:mysql://localhost:3306/hospital_db";
private static final String DB_USER = "your_mysql_username"; // e.g., "root"
private static final String DB_PASSWORD = "your_mysql_password"; // e.g., "password"

Add MySQL JDBC Driver:

Download the MySQL Connector/J.

Add the downloaded .jar file to your project's classpath (usually by adding it as a library in your IDE).

Usage
Compile and Run: Run the HospitalManagementSystem.java file from your IDE.

Interact: Follow the on-screen console prompts to perform actions like adding patients, viewing doctors, and booking appointments.

Welcome to Hospital Management System!
1. Add Patient
2. View Patients
3. View Doctors
4. Book Appointment
5. Exit
Enter your choice:

Future Enhancements
GUI Implementation: Transition from a console-based interface to a graphical user interface (e.g., JavaFX or Swing).

Advanced Appointment Management: Add features to view, update, or cancel existing appointments.

User Authentication: Implement login functionality for different user roles (e.g., admin, doctor, patient).

More Entities: Introduce additional entities like medical records, billing, or prescription management.

Error Logging: Implement a more robust error logging mechanism.

Contributing
Feel free to fork the repository and submit pull requests. For major changes, please open an issue first to discuss what you would like to change.

License
This project is licensed under the MIT License - see the LICENSE file for details.
