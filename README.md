# LinkedInProjects
# Makeup Store Management System

### By Reema F. Almukhlifi

This project is a **Makeup Store Management System** developed using Java. It focuses on:
- Organizing customer data.
- Linking customers to multiple addresses.
- Managing orders efficiently.
- Applying Object-Oriented Programming (OOP) principles for modularity and scalability.

---

## **Features**
- **Customer Management:** Dynamically stores and organizes customer information.
- **Address Management:** Links customers with multiple addresses.
- **Order Management:** Associates orders with customers and their respective addresses.
- **Scalability:** The design allows future enhancements, such as adding products or generating detailed reports.

---

## **How to Run**
1. Clone the repository:
   ```bash
   git clone https://github.com/iRemaF/LinkedInProjects.git

package store;

public class Address {

    private String city;
    private String district;
    private String street;
    private int houseNo;

    // Constructor: Initializes the Address object with city, district, street, and houseNo.
    public Address(String city, String district, String street, int houseNo) {
        setCity(city);
        setDistrict(district);
        setStreet(street);
        setHouseNo(houseNo);
    }

    // Getter and Setter methods for City
    public String getCity() {
        return city;
    }

    public void setCity(String city) {
        this.city = city;
    }

    // Getter and Setter methods for District
    public String getDistrict() {
        return district;
    }

    public void setDistrict(String district) {
        this.district = district;
    }

    // Getter and Setter methods for Street
    public String getStreet() {
        return street;
    }

    public void setStreet(String street) {
        this.street = street;
    }

    // Getter and Setter methods for HouseNo
    public int getHouseNo() {
        return houseNo;
    }

    public void setHouseNo(int houseNo) {
        this.houseNo = houseNo;
    }

    @Override
    // Converts the Address object into a readable string format.
    public String toString() {
        return String.format("%s - %s, %s %d", getCity(), getDistrict(), getStreet(), getHouseNo());
    }
}
