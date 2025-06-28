# Makeup Store Management System

### By Reema F. Almukhlifi

This project is a Java-based system developed to manage customer records, associated addresses, and their makeup orders.
It was built as part of our university coursework to demonstrate the use of object-oriented programming (OOP), custom class design, and real-world store simulation.

---

## Project Overview

The system focuses on:

* Structuring customer data with flexibility
* Allowing each customer to have multiple addresses
* Managing order placement and linking it to customer and location
* Modeling realistic store behavior using object-oriented principles

---

## Features

* **Customer Management**: Creates customers with unique IDs and personal details
* **Address Management**: Allows one customer to have multiple delivery addresses
* **Order Management**: Supports order creation and tracking per customer/address
* **OOP Design**: Each entity (Customer, Address, Order, Store) is separated into clean classes

---

## Technologies Used

* Java
* Object-Oriented Programming
* GitHub – for version control

---

## How to Run

Clone the repository:

```bash
git clone https://github.com/iRemaF/LinkedInProjects.git
```

Open the project in your preferred Java IDE (IntelliJ IDEA, NetBeans, etc.) and compile and run the main class that contains `main()`.

---

## Code

### `Address.java`

```java
package store;

public class Address {

    private String city;
    private String district;
    private String street;
    private int houseNo;

    public Address(String city, String district, String street, int houseNo) {
        setCity(city);
        setDistrict(district);
        setStreet(street);
        setHouseNo(houseNo);
    }

    public String getCity() { return city; }
    public void setCity(String city) { this.city = city; }

    public String getDistrict() { return district; }
    public void setDistrict(String district) { this.district = district; }

    public String getStreet() { return street; }
    public void setStreet(String street) { this.street = street; }

    public int getHouseNo() { return houseNo; }
    public void setHouseNo(int houseNo) { this.houseNo = houseNo; }

    @Override
    public String toString() {
        return String.format("%s - %s, %s %d", getCity(), getDistrict(), getStreet(), getHouseNo());
    }
}
```

---

### `Customer.java`

```java
package store;

import java.util.ArrayList;

public class Customer {

    private int id;
    private String name;
    private ArrayList<Address> addresses;

    public Customer(int id, String name) {
        this.id = id;
        this.name = name;
        addresses = new ArrayList<>();
    }

    public void addAddress(Address address) {
        addresses.add(address);
    }

    public ArrayList<Address> getAddresses() {
        return addresses;
    }

    public String getName() {
        return name;
    }

    public int getId() {
        return id;
    }

    @Override
    public String toString() {
        return String.format("Customer #%d: %s", id, name);
    }
}
```

---

### `Order.java`

```java
package store;

public class Order {

    private int orderNumber;
    private Customer customer;
    private Address deliveryAddress;

    public Order(int orderNumber, Customer customer, Address deliveryAddress) {
        this.orderNumber = orderNumber;
        this.customer = customer;
        this.deliveryAddress = deliveryAddress;
    }

    public int getOrderNumber() {
        return orderNumber;
    }

    public Customer getCustomer() {
        return customer;
    }

    public Address getDeliveryAddress() {
        return deliveryAddress;
    }

    @Override
    public String toString() {
        return String.format("Order #%d for %s at %s", orderNumber, customer.getName(), deliveryAddress);
    }
}
```

---

### `Store.java`

```java
package store;

import java.util.ArrayList;

public class Store {

    private ArrayList<Customer> customers;
    private ArrayList<Order> orders;

    public Store() {
        customers = new ArrayList<>();
        orders = new ArrayList<>();
    }

    public void addCustomer(Customer customer) {
        customers.add(customer);
    }

    public void placeOrder(Order order) {
        orders.add(order);
    }

    public void displayAllOrders() {
        for (Order order : orders) {
            System.out.println(order);
        }
    }

    public void displayCustomers() {
        for (Customer customer : customers) {
            System.out.println(customer);
        }
    }
}
```

---

## GitHub Repository

[View the Repository](https://github.com/iRemaF/LinkedInProjects/blob/main/Makeup%20Store%20Management%20System.md)

---

## Contact

For questions or collaboration, feel free to reach out:

* **GitHub**: [github.com/iRemaF](https://github.com/iRemaF)  
* **LinkedIn**:[https://linkedin.com](https://www.linkedin.com/in/reema-almukhlifi-bbb2b1240/)

---
