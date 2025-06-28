# DTP Admission System

### By Reema F. Almukhlifi

This project presents a Java-based admission system developed for managing and processing student applications for undergraduate programs.
It was built as part of our university Data Structures course to demonstrate the use of object-oriented programming, custom data structures, and logical filtering and sorting in real-world simulations.

---

## Project Overview

The system simulates a university admission process and handles:

* Student applications
* GPA-based filtering
* Course-level eligibility checks
* Sorting applicants based on academic performance
* Program assignment based on student preferences and seat availability

We focused on applying custom-built data structures and algorithmic logic to mirror realistic academic admission scenarios.

---

## System Structure

The system includes the following core components:

* **LLQueue** – A custom queue class to manage incoming student applications
* **LLstack** – A custom stack class used for sorting and assigning students
* **Student** – Represents individual applicants, including name, ID, courses, grades, and desired majors
* **UnderGraduateProgram** – Represents available programs (CS, IS, IT) with limited seat capacity
* **Admission** – The main class responsible for filtering, ordering, and assigning applicants

---

## Key Features

* Admission Threshold: Filters students with a total grade below 540
* Course Filtering: Accepts only students who scored 90+ in all courses
* Performance Sorting: Orders students using a custom stack based on performance
* Program Assignment: Assigns students to their first available desired major
* Modular Design: Organized using object-oriented principles and reusable methods

---

## Technologies Used

* **Java** – Main programming language
* **Custom Data Structures** – Queue and Stack built using linked lists
* **Object-Oriented Programming** – Encapsulation, inheritance, abstraction
* **GitHub** – For version control and collaboration
* **VS Code** – For development and testing  
---

## How to Run

Clone the repository:

```bash
git clone https://github.com/iRemaF/DTP-Admission-System.git
```

```java
// by Reema F. Almukhlifi
// This project simulates a university admission system using Java and custom data structures

public class Admission {
    private final double ACCEPTANCETHRESHOLD = 540;
    private LLQueue<Student> applicants;
    private LLstack<Student> Candidate;
    private UnderGraduateProgram CS;
    private UnderGraduateProgram IS;
    private UnderGraduateProgram IT;

    public Admission() {
        applicants = new LLQueue<>();
        Candidate = new LLstack<>();
        CS = new UnderGraduateProgram("CS");
        IS = new UnderGraduateProgram("IS");
        IT = new UnderGraduateProgram("IT");
    }

    public void FilterByTotalGrades() {
        int size = applicants.size();
        for (int i = 0; i < size; i++) {
            Student std = applicants.dequeue();
            if (std.TotalGrades() >= ACCEPTANCETHRESHOLD) {
                applicants.enqueue(std);
            }
        }
    }

    public boolean CheckStudentCoursesGraterThean90(Student std) {
        SinglyLinkedList grades = std.getGrades();
        Node temp = grades.head;
        while (temp != null) {
            if (temp.getElement().getGrade() < 90) {
                return false;
            }
            temp = temp.getNext();
        }
        return true;
    }

    public void AssignStudenttoProgram() {
        while (!Candidate.isEmpty()) {
            Student candidate = Candidate.pop();
            LLstack<UnderGraduateProgram> preferences = candidate.getDesiredMajors();
            while (!preferences.isEmpty()) {
                UnderGraduateProgram major = preferences.pop();
                if (major.IsSeatAvailabile()) {
                    candidate.setMajor(major.getUnderGraduateProgramName());
                    major.incrementSeats();
                    break;
                }
            }
            System.out.println(candidate);
        }
    }
}
```

---

## GitHub Repository

[View the Repository](https://github.com/iRemaF/LinkedInProjects/blob/main/DTP%20Admission%20System.md)

---

## Contact

For questions or collaboration, feel free to reach out:

* **GitHub**: [github.com/iRemaF](https://github.com/iRemaF)  
* **LinkedIn**:[https://linkedin.com](https://www.linkedin.com/in/reema-almukhlifi-bbb2b1240/)

---
