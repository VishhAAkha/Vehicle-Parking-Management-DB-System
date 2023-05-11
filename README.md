-- Create the database
CREATE DATABASE ParkingManagementSystem;

-- Switch to the newly created database
USE ParkingManagementSystem;

-- Create table for parking spaces
CREATE TABLE ParkingSpaces (
    space_id INT PRIMARY KEY,
    vehicle_type VARCHAR(50),
    is_available BIT
);

-- Create table for payments
CREATE TABLE Payments (
    payment_id INT PRIMARY KEY,
    space_id INT,
    vehicle_type VARCHAR(50),
    payment_amount DECIMAL(10, 2),
    payment_method VARCHAR(50),
    payment_date DATETIME,
    FOREIGN KEY (space_id) REFERENCES ParkingSpaces(space_id)
);

