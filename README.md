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

![Screenshot 2024-11-14 191947](https://github.com/user-attachments/assets/0c40f6b7-bb26-4228-bf29-7d5fe9452df9)
![Screenshot 2024-11-14 191906](https://github.com/user-attachments/assets/b308f436-dd39-40b4-af7e-3c5257e445fe)
![Screenshot 2024-11-14 191850](https://github.com/user-attachments/assets/12cf381d-aa7e-47c0-a14d-a1eafc2f0908)
![Screenshot 2024-11-14 191828](https://github.com/user-attachments/assets/1d24b365-619a-49ea-a5be-1eee6d5f31f7)
![Screenshot 2024-11-14 191818](https://github.com/user-attachments/assets/f13e85e1-ea7b-4408-b87b-eb34868a6bfd)
![Screenshot 2024-11-14 191627](https://github.com/user-attachments/assets/1f337ef1-2450-4de8-a654-033e2240242d)
![Screenshot 2024-11-14 191612](https://github.com/user-attachments/assets/759e404d-4e45-41e5-b36a-efdd10120feb)
![Screenshot 2024-11-14 191600](https://github.com/user-attachments/assets/f434cfd6-e547-48f3-a3bc-7a62e2c7ec2b)
![Screenshot 2024-11-14 191526](https://github.com/user-attachments/assets/e4a6ba17-5067-47a1-b091-acf8fcde7390)
![Screenshot 2024-11-14 191514](https://github.com/user-attachments/assets/c3e7ef27-d4fd-4b77-a4a6-0ea5c2fa0df9)
![Screenshot 2024-11-14 191506](https://github.com/user-attachments/assets/cc54f33b-1eef-477c-a2b8-f9cde37e5e79)
![Screenshot 2024-11-14 191257](https://github.com/user-attachments/assets/1cadc10c-0f65-4884-8e38-1163efff0b2a)
![Screenshot 2024-11-14 191243](https://github.com/user-attachments/assets/a59bf190-ebed-4c79-99b2-bc8bdd081cbe)
![Screenshot 2024-11-14 191234](https://github.com/user-attachments/assets/edc54268-6908-4723-9ae4-c81f0b9fb91e)
![Screenshot 2024-11-14 191221](https://github.com/user-attachments/assets/1b02b0d5-3702-429a-80ef-57b30776a766)
![Screenshot 2024-11-14 191109](https://github.com/user-attachments/assets/45fa4d59-e349-457d-835b-e6063caa4f98)
![Screenshot 2024-11-14 191059](https://github.com/user-attachments/assets/d22ade02-3e61-4309-8fbf-026433bddc7e)
![Screenshot 2024-11-14 191027](https://github.com/user-attachments/assets/7182df68-c983-4988-b618-9cd15407cadd)
![Screenshot 2024-11-14 191010](https://github.com/user-attachments/assets/b8921e31-cd21-44d3-9fbf-e739aeeec5d8)
![Screenshot 2024-11-14 190956](https://github.com/user-attachments/assets/a2ff8f01-88ae-4335-86b7-18dd29e4090f)
![Screenshot 2024-11-14 190932](https://github.com/user-attachments/assets/d63be1c7-8564-4de2-9bfc-b5aed44a7733)
![Screenshot 2024-11-14 190912](https://github.com/user-attachments/assets/1c5ee1cb-c884-4933-8823-32929e9b9362)
![Screenshot 2024-11-14 190426](https://github.com/user-attachments/assets/d0ce16f4-c0ee-4605-87f7-4bcb97ca41e5)
![Screenshot 2024-11-14 190402](https://github.com/user-attachments/assets/0b0e33d0-d16d-4f63-bd61-f65087c1b84f)


