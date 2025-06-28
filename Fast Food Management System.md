# Fast Food Management System

### By Reema F. Almukhlifi

This project demonstrates an advanced **fast food management system** developed using Java and Object-Oriented Programming (OOP) principles.
It simulates the ordering workflow of a restaurant, focusing on organized customer data, address management, and structured order handling.

---

## Project Overview

The system focuses on:

* Efficiently organizing customer information
* Linking each customer to one or more delivery addresses
* Managing orders and associating them with correct customers and addresses
* Designing a scalable structure ready for future expansions

---

## Features

* **Customer Management**: Maintains detailed records for each customer
* **Address Management**: Supports multiple addresses per customer
* **Order Management**: Tracks and displays orders linked to customer profiles
* **Scalability**: The architecture can be extended to include menus, pricing, and payment systems

---

## Technologies Used

* **Java** – Core programming language
* **OOP Concepts** – Including abstraction, encapsulation, and modularity
* **GitHub** – For version control and code hosting

---

## How to Run

1. Clone the repository:

```bash
git clone https://github.com/iRemaF/FastFoodManagement.git
```

2. Open the project in any Java IDE such as IntelliJ IDEA or NetBeans.
3. Compile and run the `Main.java` class.

---

## Code

### `Address.java`

```java
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
```

---

### `Customer.java`

```java
package fastfood;

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
package fastfood;

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

### `Restaurant.java`

```java
package fastfood;

import java.util.ArrayList;

public class Restaurant {

    private ArrayList<Customer> customers;
    private ArrayList<Order> orders;

    public Restaurant() {
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

### `Main.java`

```java
package fastfood;

public class Main {

    public static void main(String[] args) {
        // Create the restaurant system
        Restaurant restaurant = new Restaurant();

        // Create customers
        Customer c1 = new Customer(1, "Reema");
        Customer c2 = new Customer(2, "Alanoud");

        // Add addresses to customers
        c1.addAddress(new Address("Riyadh", "Al-Malaz", "Olaya St", 101));
        c1.addAddress(new Address("Riyadh", "Al-Nakheel", "Takhassusi St", 102));
        c2.addAddress(new Address("Jeddah", "Al-Rawdah", "Hira St", 201));

        // Add customers to restaurant
        restaurant.addCustomer(c1);
        restaurant.addCustomer(c2);

        // Place orders for customers
        Order o1 = new Order(1001, c1, c1.getAddresses().get(0));
        Order o2 = new Order(1002, c2, c2.getAddresses().get(0));
        Order o3 = new Order(1003, c1, c1.getAddresses().get(1));

        restaurant.placeOrder(o1);
        restaurant.placeOrder(o2);
        restaurant.placeOrder(o3);

        // Display all customers
        System.out.println("All Customers:");
        restaurant.displayCustomers();

        System.out.println("\nAll Orders:");
        restaurant.displayAllOrders();
    }
}
```

---

## GitHub Repository

[View the Repository](https://github.com/iRemaF/LinkedInProjects/blob/main/Fast%20Food%20Management%20System.md)

---

## Contact

For questions or collaboration, feel free to reach out:

* **GitHub**: [github.com/iRemaF](https://github.com/iRemaF)  
* **LinkedIn**:[https://linkedin.com](https://www.linkedin.com/in/reema-almukhlifi-bbb2b1240/)


---
