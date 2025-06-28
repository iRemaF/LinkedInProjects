🎓 DTP Admission System
👩‍💻 By Reema F. Almukhlifi
This project presents a Java-based admission system designed to manage the selection and assignment of students into undergraduate programs based on their academic performance and preferences.
It was developed as part of a Data Structures course to demonstrate mastery in object-oriented programming, custom linked structures, and logical decision-making in educational systems.

📌 Project Overview
The system simulates a university admission process and manages:

Student applications

GPA-based filtering

Preference-based program assignment

Custom stack & queue operations

Sorting and eligibility checks

We focused on clean modular design, data structure implementation, and simulating real-world admission behavior.

🧩 System Structure
The project includes the following components:

LLQueue & LLstack – Custom-built queue and stack using linked lists

Student – Stores name, ID, grades, and desired majors

Course – Represents course name and grade

UnderGraduateProgram – Represents CS, IS, and IT programs with seat limits

Admission – Main logic handling admission, filtering, and assignment

✨ Key Features
🎯 Threshold-based Filtering: Only applicants with total grades above 540 are considered

📋 Course-level Filtering: Students must score 90+ in all courses to proceed

🧠 Sorted Stack Allocation: Students are ordered and processed by performance

🏛 Smart Assignment: Students are assigned to their first available preferred major

🔄 Reusable Design: Modular, expandable, and readable class structure

🛠 Technologies Used
Java – Core programming language

OOP Principles – Encapsulation, abstraction, modularity

Custom Data Structures – Linked-list-based queue and stack

NetBeans / IntelliJ IDEA – IDEs used for development and testing

▶️ How to Run
Clone the repository:
git clone https://github.com/iRemaF/DTP-Admission-System.git
// By Reema F. Almukhlifi
// This project simulates a university admission system based on GPA thresholds and program preferences.

package project;

import project.SinglyLinkedList.Node;

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

    public void FillApplicantions() {
        // Student initialization with desired majors and grades
        // Applicants are added to the queue here
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

    public void FilterByCourses() {
        int size = applicants.size();
        for (int i = 0; i < size; i++) {
            Student std = applicants.dequeue();
            if (CheckStudentCoursesGraterThean90(std)) {
                applicants.enqueue(std);
            }
        }
    }

    public boolean CheckStudentCoursesGraterThean90(Student std) {
        SinglyLinkedList gradeList = std.getGrades();
        Node temp = gradeList.head;
        while (temp != null) {
            if (temp.getElement().getGrade() < 90) {
                return false;
            }
            temp = temp.getNext();
        }
        return true;
    }

    public void ArrangeStudentsInStack() {
        int size = applicants.size();
        for (int i = 0; i < size; i++) {
            Student std = applicants.dequeue();
            applicants.enqueue(std);
            Student minStd = minimumLevelStudent();
            RemoveMinimumLevelStudent(minStd);
            Candidate.push(minStd);
        }
    }

    public Student minimumLevelStudent() {
        Student minStd = applicants.first();
        int size = applicants.size();
        for (int i = 0; i < size; i++) {
            Student std = applicants.dequeue();
            if (std.TotalGrades() < minStd.TotalGrades()) {
                minStd = std;
            }
            applicants.enqueue(std);
        }
        return minStd;
    }

    public Student RemoveMinimumLevelStudent(Student minLevelStudent) {
        int size = applicants.size();
        for (int i = 0; i < size; i++) {
            Student std = applicants.dequeue();
            if (std != minLevelStudent) {
                applicants.enqueue(std);
            }
        }
        return minLevelStudent;
    }

    public void AssignStudenttoProgram() {
        while (!Candidate.isEmpty()) {
            Student candidate = Candidate.pop();
            LLstack<UnderGraduateProgram> desiredMajorsStack = candidate.getDesiredMajors();
            while (!desiredMajorsStack.isEmpty()) {
                UnderGraduateProgram desiredMajor = desiredMajorsStack.pop();
                if (desiredMajor.IsSeatAvailabile()) {
                    candidate.setMajor(desiredMajor.getUnderGraduateProgramName());
                    desiredMajor.incrementSeats();
                    break;
                }
            }
            System.out.println(candidate);
            System.out.println("----------------------------------");
        }
    }
}
GitHub Repository
View the Repository

Contact
For questions or collaboration, feel free to get in touch.

