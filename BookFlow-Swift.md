# 📚 BookFlow-Swift — Library Logic System

*Swift 102| Advanced OOP Implementation*

> **BookFlow-Swift** is a concise management engine built to implement core Swift concepts: Classes, Optionals, and Access Control.

---

## Project Overview
This project serves as a functional implementation of a library inventory system. It replaces manual tracking with automated logic to handle book data, stock levels, and sales transactions securely.

**Core Objectives:**
* **Logic Flow:** Implementing clean `if-else` and `guard` statements.
* **Data Safety:** Using Optionals to handle missing values safely.
* **Encapsulation:** Protecting system data using `private` modifiers.

---

## Key Features
* **Full CRUD Operations:** Add, Search, Update, and Delete books.
* **Transactional Logic:** Atomic stock deduction during sales.
* **Error Trapping:** Handling "Out of Stock" or "Missing Item" scenarios.
* **Dynamic Reports:** Real-time inventory status printing.

---

## Tools & Technologies
![Swift](https://img.shields.io/badge/Swift-FA7343?style=for-the-badge&logo=swift&logoColor=white)
![Xcode](https://img.shields.io/badge/Xcode-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white)

---

## 💻 Full Implementation Code

```swift
import Foundation

class Book {
    let id: Int
    var title: String
    var author: String
    var price: Double? 
    var quantity: Int
    
    init(id: Int, title: String, author: String, price: Double?, quantity: Int) {
        self.id = id
        self.title = title
        self.author = author
        self.price = price
        self.quantity = quantity
    }
}

class BookFlowManager {
    private var books: [Book] = []
    
    // 1. Add Book
    func addBook(_ book: Book) {
        books.append(book)
    }
    
    // 2. Search Book
    func findBook(id: Int) -> Book? {
        return books.first { $0.id == id }
    }
    
    // 3. Remove Book
    func removeBook(id: Int) {
        books.removeAll { $0.id == id }
    }
    
    // 4. Process Sale (Transactional Logic)
    func sellBook(id: Int, amount: Int) {
        guard let book = findBook(id: id) else {
            print("❌ Error: Book ID \(id) not found.")
            return
        }
        
        if book.quantity >= amount {
            book.quantity -= amount
            let total = (book.price ?? 0.0) * Double(amount)
            print("✅ Sold \(amount)x '\(book.title)'. Total: \(total) SAR")
        } else {
            print("❌ Error: Insufficient stock for '\(book.title)'.")
        }
    }
    
    // 5. Display Inventory
    func printInventory() {
        print("\n--- Current Inventory ---")
        for book in books {
            let p = book.price != nil ? "\(book.price!)" : "N/A"
            print("ID: \(book.id) | \(book.title) | Stock: \(book.quantity) | Price: \(p)")
        }
    }
}

// --- Execution ---
let manager = BookFlowManager()
manager.addBook(Book(id: 1, title: "Start with why", author: "Simon Sinek", price: 80.0, quantity: 13))
manager.addBook(Book(id: 2, title: "Clean Code", author: "Robert Martin", price: 50.0, quantity: 5))

manager.printInventory()
manager.sellBook(id: 1, amount: 3)
manager.printInventory()
```
---
## Contact

* **GitHub:** [iRemaF](https://github.com/iRemaF/LinkedInProjects)
* **LinkedIn:** [Reema F. Almukhlifi](https://www.linkedin.com/in/reema-f-almukhlifi-bbb2b1240)
