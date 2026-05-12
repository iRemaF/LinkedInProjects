# 🤝 VolunteerFlow-Swift — Advanced Enrollment System

*Swift 103 | Generics, Error Handling & Protocol-Oriented Design*

> **VolunteerFlow-Swift** is an advanced registration engine designed to process diverse volunteer categories using Type-Safe Generics and robust Error Validation.

---

## Project Overview
This project evolves basic enrollment into a professional-grade pipeline. By utilizing **Generics**, the system can manage multiple volunteer types without duplicating code, while **Protocol Extensions** ensure consistent behavior across the entire application.

**Core Objectives:**
* **Reusable Logic:** Implementing Generic Controllers for different volunteer roles.
* **Complex Validation:** Handling edge cases through custom Swift Errors.
* **Protocol-Oriented Design:** Using `CustomStringConvertible` to standardize system output.

---

## Key Features
* **Generic Enrollment:** One engine to handle any volunteer type (`Medical`, `General`, etc.).
* **Advanced Error Trapping:** Multi-layered `do-catch` blocks for precise user feedback.
* **Data Integrity:** Enforcing 10-digit numeric constraints via `guard` statements.
* **Modular Architecture:** Separating validation logic from data storage for better maintainability.

---

## Tools & Technologies
![Swift](https://img.shields.io/badge/Swift-FA7343?style=for-the-badge&logo=swift&logoColor=white)
![Xcode](https://img.shields.io/badge/Xcode-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white)

---

## 💻 Advanced Implementation Code

```swift
import Foundation

// MARK: - Core Protocols & Errors
enum EnrollmentError: Error {
    case invalidPhoneFormat
    case underaged(required: Int)
}

protocol UserProfile: CustomStringConvertible {
    var name: String { get }
    var age: Int { get }
}

// MARK: - Models
struct GeneralVolunteer: UserProfile {
    let name: String
    let phone: String
    let age: Int
    
    var description: String {
        return "Volunteer [General]: \(name) | Age: \(age)"
    }
}

// MARK: - Advanced Generic Engine
class EnrollmentEngine<T: UserProfile> {
    private var database: [T] = []
    
    // Generic validation and registration
    func process(applicant: T, phone: String) throws {
        // 1. Validate Phone
        guard phone.count == 10, phone.allSatisfy({ $0.isNumber }) else {
            throw EnrollmentError.invalidPhoneFormat
        }
        
        // 2. Validate Age
        guard applicant.age >= 18 else {
            throw EnrollmentError.underaged(required: 18)
        }
        
        // 3. Save to Database
        database.append(applicant)
        print("✅ Success: \(applicant.description) has been enrolled.")
    }
}

// --- Execution ---
let engine = EnrollmentEngine<GeneralVolunteer>()
let applicant = GeneralVolunteer(name: "Reema", phone: "0501234567", age: 24)

do {
    try engine.process(applicant: applicant, phone: "0501234567")
} catch EnrollmentError.invalidPhoneFormat {
    print("❌ Error: Phone must be 10 digits (numbers only).")
} catch EnrollmentError.underaged(let required) {
    print("❌ Error: Applicants must be at least \(required) years old.")
} catch {
    print("❌ Unexpected error occurred.")
}
```
---
## Contact

* **GitHub:** [iRemaF](https://github.com/iRemaF/LinkedInProjects)
* **LinkedIn:** [Reema F. Almukhlifi](https://www.linkedin.com/in/reema-f-almukhlifi-bbb2b1240)
