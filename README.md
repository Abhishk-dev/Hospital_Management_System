#Hospital Management System : 
 - Overview
The Hospital Management System (HMS) is a web-based Java application designed to streamline and manage various operations of a hospital.
It provides a comprehensive solution for managing patient data, doctor profiles, appointments, and administrative tasks.
This project is built using Java (Servlets, JSP), and MySQL as the backend database to store and manage all hospital-related data.

-Features
Admin Login: Secure admin login functionality for managing doctors, patients, and appointments.
Doctor Management: Admin can add, update, view, and delete doctor profiles.
Patient Management: Allows for patient registration and viewing patient information.
Appointment Scheduling: Easy appointment booking system for patients with doctors.
Doctor-Patient Interaction: Doctors can view their appointment schedules and patient details.
Responsive Design: User-friendly interface for both admin and users.
Session Management: Secure session handling for admin and doctor login.
Technologies Used
Java (Servlets & JSP): Backend development
MySQL: Database management
JDBC: Database connectivity
Apache Tomcat: Application server
HTML5/CSS3: Frontend design
Bootstrap: For responsive UI design
JSTL: For dynamic content rendering in JSP

#Prerequisites
Before you begin, ensure you have the following installed:

Java JDK (21 or higher)
Apache Tomcat (9.x or higher)
MySQL (8.x or higher)

# Technology used in this project: 
Advance JAVA concepts like JSP, JSTL, Servlet, HTML, CSS, Boostrap 5, Fontawesome and MySQL

---------------------------------------------------------------------------------------------------------------------
# create the database on MySQL Workbench to run this Web Application : 
-- Creating the 'hospital' database and using it
CREATE DATABASE IF NOT EXISTS hospital;
USE hospital;

-- User Details Table
CREATE TABLE IF NOT EXISTS user_details (
    id INT AUTO_INCREMENT PRIMARY KEY,
    full_name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL
);

-- Appointment Table
CREATE TABLE IF NOT EXISTS appointment (
    id INT AUTO_INCREMENT PRIMARY KEY,
    userId INT NOT NULL,
    fullName VARCHAR(255) NOT NULL,
    gender VARCHAR(10) NOT NULL,
    age VARCHAR(3) NOT NULL,
    appointmentDate DATE NOT NULL,
    email VARCHAR(255) NOT NULL,
    phone VARCHAR(15) NOT NULL,
    diseases TEXT NOT NULL,
    doctorId INT NOT NULL,
    address VARCHAR(255) NOT NULL,
    status VARCHAR(50) NOT NULL,
    FOREIGN KEY (doctorId) REFERENCES doctor(id) ON DELETE CASCADE
);

-- Doctor Table
CREATE TABLE IF NOT EXISTS doctor (
    id INT AUTO_INCREMENT PRIMARY KEY,
    fullName VARCHAR(255) NOT NULL,
    dateOfBirth DATE NOT NULL,
    qualification VARCHAR(255) NOT NULL,
    specialist VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL UNIQUE,
    phone VARCHAR(20) NOT NULL,
    password VARCHAR(255) NOT NULL
);

-- Specialist Table
CREATE TABLE IF NOT EXISTS specialist (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL
);

-- Inserting doctor records into the doctor table
INSERT INTO doctor (fullName, dateOfBirth, qualification, specialist, email, phone, password)
VALUES 
    ('Dr. John Doe', '1975-08-15', 'MBBS, MD', 'Cardiologist', 'johndoe@example.com', '123-456-7890', 'password123'),
    ('Dr. Jane Smith', '1980-03-22', 'MBBS, MD', 'Neurologist', 'janesmith@example.com', '987-654-3210', 'password456'),
    ('Dr. Emily Johnson', '1985-06-10', 'MBBS, MD', 'Pediatrician', 'emilyjohnson@example.com', '555-123-4567', 'password789'),
    ('Dr. Michael Brown', '1978-11-02', 'MBBS, MS', 'Orthopedic', 'michaelbrown@example.com', '321-654-9870', 'password101'),
    ('Dr. Sarah Wilson', '1982-01-25', 'MBBS, MS', 'General Surgeon', 'sarahwilson@example.com', '432-123-7890', 'password102'),
    ('Dr. David Lee', '1979-09-17', 'MBBS, MD', 'Dermatologist', 'davidlee@example.com', '987-321-6540', 'password103'),
    ('Dr. Laura Clark', '1983-04-05', 'MBBS, MD', 'Psychiatrist', 'lauraclark@example.com', '555-987-6543', 'password104'),
    ('Dr. James Taylor', '1986-07-19', 'BDS', 'Dentist', 'jamestaylor@example.com', '789-321-6549', 'password105');

-- Selecting all users from user_details
SELECT * FROM user_details;



