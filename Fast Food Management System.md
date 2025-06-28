# Fast Food Management System
## By Reema F. Almukhlifi
This project demonstrates an **advanced fast food management system** developed using Java and Object-Oriented Programming (OOP) principles.  
It focuses on:
- Organizing customer data efficiently.
- Linking customers to multiple addresses.
- Managing orders effectively.
- Ensuring flexibility and scalability with OOP.
---
## Features
- **Customer Management:** Handles customer data efficiently.
- **Address Management:** Links customers to their respective addresses.
- **Order Management:** Manages orders with accuracy and speed.
- **Scalability:** The system allows future expansion and enhancements.
---
## Technologies Used
- **Java:** The core programming language used.
- **OOP Principles:** Encapsulation, abstraction, and modularity applied.
- **GitHub:** For version control and collaboration.
---
## How to Run
1. Clone the repository:

```bash
git clone https://github.com/iRemaF/FastFoodManagement.git

// by Reema F. Almukhlifi
// This project demonstrates an advanced fast food management system

package fastfood;

public class Address {

    private String district; // District name
    private String street;
    private int houseNo;

    // Default constructor
    public Address() {
        this("", "", 0);
    }

    // Parameterized constructor
    public Address(String district, String street, int houseNo) {
        setDistrict(district);
        setStreet(street);
        setHouseNo(houseNo);
    }

    // Getter and Setter methods
    public String getDistrict() { return district; }
    public void setDistrict(String district) { this.district = district; }

    public String getStreet() { return street; }
    public void setStreet(String street) { this.street = street; }

    public int getHouseNo() { return houseNo; }
    public void setHouseNo(int houseNo) { this.houseNo = houseNo; }

    @Override
    public String toString() {
        return String.format("%s  %s  %d", getDistrict(), getStreet(), getHouseNo());
    }
}
