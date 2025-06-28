---

# E-commerce Database Management System

### By Reema F. Almukhlifi, Huson Mufti, Alhanouf Alqarawi

This project presents a relational **SQL-based database system** developed for managing operations in an e-commerce environment.
It was built as part of our university Database course to demonstrate data integrity, normalization, and real-world entity relationships.

---

## Project Overview

The system simulates an e-commerce store and handles:

* Customer orders
* Delivery logistics
* Shop details
* Receiver information
* Location mapping

We focused on **data normalization**, **relational structure**, and the use of **Primary and Foreign Keys** to ensure consistency and reliability across the database.

---

## Database Schema

The database includes the following tables:

* **Sender** – Stores sender details (phone, name)
* **Orders** – Tracks order placement linked to senders and shops
* **Shop** – Contains store names and types
* **Delivery** – Manages delivery agents and their assigned shops
* **Receiver** – Connects deliveries to recipients
* **RecLocation** – Maps receiver phone numbers to physical locations

All tables are interlinked through **foreign keys** to preserve data relationships and prevent duplication.

---

## Key Features

* **Data Integrity**: Enforced via Primary & Foreign Keys
* **Normalized Design**: Reduces redundancy and improves performance
* **Realistic Modeling**: Simulates a full e-commerce flow
* **Team Collaboration**: Built in collaboration and version-controlled

---

## Technologies Used

* **SQL (Oracle dialect)** – Main database language
* **ERD Design Tools** – For planning schema
* **GitHub** – For version control and collaboration

---

## How to Run

1. Clone the repository:

```bash
git clone https://github.com/iRemaF/Ecommerce-Database-SQL.git
```

2. Run the following SQL script in your Oracle SQL environment:

```sql
-- by Reema F. Almukhlifi, Huson Mufti, Alhanouf Alqarawi
-- This project demonstrates a relational database system for e-commerce management

-- Drop and create Sender table
DROP TABLE Sender CASCADE CONSTRAINT;

CREATE TABLE Sender (
    SphoneNum NUMBER(10),
    name VARCHAR2(255),
    CONSTRAINT sender_PK PRIMARY KEY (SphoneNum)
);

-- Drop and create Shop table
DROP TABLE Shop CASCADE CONSTRAINT;

CREATE TABLE Shop (
    Sname VARCHAR2(255),
    type VARCHAR2(255),
    CONSTRAINT shop_PK PRIMARY KEY (Sname)
);

-- Drop and create Orders table
DROP TABLE Orders CASCADE CONSTRAINT;

CREATE TABLE Orders (
    SphoneNum NUMBER(10),
    Sname VARCHAR2(255),
    CONSTRAINT order_FK1 FOREIGN KEY (SphoneNum) REFERENCES Sender (SphoneNum),
    CONSTRAINT order_FK2 FOREIGN KEY (Sname) REFERENCES Shop (Sname)
);

-- Drop and create Delivery table
DROP TABLE Delivery CASCADE CONSTRAINT;

CREATE TABLE Delivery (
    DphoneNum NUMBER(10),
    Sname VARCHAR2(255),
    name VARCHAR2(255),
    CONSTRAINT Delivery_PK PRIMARY KEY (DphoneNum),
    CONSTRAINT Delivery_FK FOREIGN KEY (Sname) REFERENCES Shop (Sname)
);

-- Drop and create Receiver table
DROP TABLE Receiver CASCADE CONSTRAINT;

CREATE TABLE Receiver (
    Sname VARCHAR2(255),
    name VARCHAR2(255),
    DphoneNum NUMBER(10),
    RphoneNum NUMBER(10),
    CONSTRAINT Receiver_FK FOREIGN KEY (Sname) REFERENCES Shop (Sname),
    CONSTRAINT Receiver_FK2 FOREIGN KEY (DphoneNum) REFERENCES Delivery (DphoneNum),
    CONSTRAINT Receiver_PK PRIMARY KEY (RphoneNum)
);

-- Drop and create RecLocation table
DROP TABLE RecLocation CASCADE CONSTRAINT;

CREATE TABLE RecLocation (
    RphoneNum NUMBER(10),
    location VARCHAR2(255),
    CONSTRAINT location_PK PRIMARY KEY (location),
    CONSTRAINT RecLocation_FK FOREIGN KEY (RphoneNum) REFERENCES Receiver (RphoneNum)
);

-- Drop and create Gift table
DROP TABLE Gift CASCADE CONSTRAINT;

CREATE TABLE Gift (
    order_number NUMBER(3),
    Sname VARCHAR2(255),
    women VARCHAR2(255),
    men VARCHAR2(255),
    choclate CHAR(3) CHECK (choclate IN ('yes','no')),
    birth_bouqet CHAR(3) CHECK (birth_bouqet IN ('yes','no')),
    graduation_bouquet CHAR(3) CHECK (graduation_bouquet IN ('yes','no')),
    wedding_bouquet CHAR(3) CHECK (wedding_bouquet IN ('yes','no')),
    DphoneNum NUMBER(10),
    RphoneNum NUMBER(10),
    CONSTRAINT gift_PK PRIMARY KEY (order_number),
    CONSTRAINT gift_FK FOREIGN KEY (Sname) REFERENCES Shop (Sname),
    CONSTRAINT gift_FK1 FOREIGN KEY (RphoneNum) REFERENCES Receiver (RphoneNum),
    CONSTRAINT gift_FK2 FOREIGN KEY (DphoneNum) REFERENCES Delivery (DphoneNum)
);

-- Insert data into tables
INSERT INTO Sender VALUES (1122334455, 'Reema');
INSERT INTO Sender VALUES (1212343400, 'Hanouf');
INSERT INTO Sender VALUES (1234512345, 'Muthalath');

INSERT INTO Shop VALUES ('Patchi', 'sweet');
INSERT INTO Shop VALUES ('Levo', 'flower');
INSERT INTO Shop VALUES ('Helens', 'cake');

INSERT INTO Orders VALUES (1122334455, 'Patchi');
INSERT INTO Orders VALUES (1212343400, 'Levo');
INSERT INTO Orders VALUES (1234512345, 'Helens');

INSERT INTO Delivery VALUES (400400400, 'Patchi', 'Square');
INSERT INTO Delivery VALUES (500500500, 'Levo', 'Rectangle');
INSERT INTO Delivery VALUES (600600600, 'Helens', 'Circle');

INSERT INTO Receiver VALUES ('Patchi', 'Ahmad', 400400400, 1234123456);
INSERT INTO Receiver VALUES ('Levo', 'Kareem', 500500500, 5432154321);
INSERT INTO Receiver VALUES ('Helens', 'Khalid', 600600600, 1213141516);

INSERT INTO RecLocation VALUES (1234123456, 'Riyadh');
INSERT INTO RecLocation VALUES (5432154321, 'Jeddah');
INSERT INTO RecLocation VALUES (1213141516, 'Dammam');

INSERT INTO Gift (order_number, Sname, DphoneNum, RphoneNum, men)
VALUES (121, 'Patchi', 400400400, 1234123456, 'oud');

INSERT INTO Gift (order_number, Sname, DphoneNum, RphoneNum, women)
VALUES (212, 'Levo', 500500500, 5432154321, 'pink party');

INSERT INTO Gift (order_number, Sname, DphoneNum, RphoneNum, birth_bouqet)
VALUES (122, 'Helens', 600600600, 1213141516, 'yes');
```

---

## GitHub Repository

[View the Repository](https://github.com/iRemaF/LinkedInProjects/blob/main/E-commerce%20Database%20Management%20System.md)

---

## Contact

For questions or collaboration, feel free to reach out:

* **GitHub**: [github.com/iRemaF](https://github.com/iRemaF)  
* **LinkedIn**: [linkedin.com/in/your-profile](https://linkedin.com/in/your-profile)

---
