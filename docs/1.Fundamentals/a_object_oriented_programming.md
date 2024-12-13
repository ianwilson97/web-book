# 🔮 Object Oriented Programming
![enter image description here](https://i.postimg.cc/k5bN3wFQ/temp-Image-KDO9-RC.avif)
## Introduction
As a software engineer, mastering programming fundamentals is fundamental to writing maintainable, scalable, and efficient code. This guide focuses on Object-Oriented Programming (OOP), one of the most important paradigms in modern software development.

## Why Object-Oriented Programming?
I've personally found OOP to be crucial so far in my journey as a software engineer. OOP is important because:

- It helps manage complex systems by breaking them into manageable pieces
- Promotes code reuse and reduces redundancy
- Makes code more maintainable and easier to debug
- Facilitates team collaboration through clear interfaces

### ✅ When to Use OOP
- When building medium to large-scale applications
- Working on long-term maintainable projects
- Developing systems with clear entity relationships
- Creating frameworks or libraries
- Working with domain-driven design

### ❌ When Not to Use OOP 

- Simple script-like programs
- One-off automation tasks
- Performance-critical systems where procedural code might be more efficient
- Functional programming scenarios

## 📘 Core Concepts
### 📦 Classes and Objects
#### What Are They?
- Class: A blueprint for creating objects, defining their properties and behaviors
- Object: An instance of a class with actual values

#### When to Create a Class
- When modeling real-world entities (e.g., User, Product)
- When grouping related functionality
- When you need multiple instances with similar properties
- When implementing a design pattern


````java
public class User {
    // Properties (state)
    private String username;
    private String email;
    
    // Constructor
    public User(String username, String email) {
        this.username = username;
        this.email = email;
    }
    
    // Methods (behavior)
    public void updateEmail(String newEmail) {
        this.email = newEmail;
    }
}
````

### 🔒 Encapsulation
#### What Is It?
Encapsulation bundles data and the methods that it operates on within a single unit, restricting direct access to some of an object's components.

#### ✅ When to Use
- Protecting internal state of objects
- Controlling access to data
- Hiding implementation details
- Enforcing validation logic

````java
public class BankAccount {
    private double balance;  // Encapsulated data
    
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        } else {
            throw new IllegalArgumentException("Deposit amount must be positive");
        }
    }
    
    public double getBalance() {
        return balance;
    }
}
````

### 🧬 Inheritance
#### What Is It?
Inheritance allows a class to inherit attributes and methods from another class, establishing an "is-a" relationship.

#### ✅ When to Use
- Creating specialized versions of classes
- Sharing common functionality among related classes
- Implementing polymorphic behavior
- Building class hierarchies

#### ❌ When Not to Use
- When there's no clear "is-a" relationship
- When you need flexibility in changing behavior
- When inheritance would create deep hierarchies
- When composition would be more appropriate

````java
public abstract class Vehicle {
    protected String brand;
    
    public abstract void start();
}

public class Car extends Vehicle {
    @Override
    public void start() {
        System.out.println("Car starting...");
    }
}
````

### 🔄 Polymorphism
#### What Is It?
Polymorphism allows objects to take multiple forms, enabling you to perform the same action in different ways.
#### Types of Polymorphism
##### 1. Compile-time (Method Overloading)
- Same method name, different parameters
- Resolve at compile time
##### 2. Runtime (Method Overriding)
- Same method signature in parent and child classes
- Resolved at runtime

#### ✅ When to Use
- Creating flexible and extensible APIs
- Implementing plugins or extensions
- Working with collections of related objects
- Building framework-level code
````java
// Method Overloading
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }
    
    public double add(double a, double b) {
        return a + b;
    }
}

// Method Overriding
public interface PaymentProcessor {
    void processPayment(double amount);
}

public class CreditCardProcessor implements PaymentProcessor {
    @Override
    public void processPayment(double amount) {
        // Credit card specific logic
    }
}
````
### 🔗 Association, Aggregation, and Composition
#### 🤝 Association
- Represents relationships between objects
- Can be one-to-one, one-to-many, or many-to-many
- Objects have independent lifecycles
#### ✅ When to Use Association
- When objects need to communicate
-  When representing relationships between independent entities
- When objects can exist independently
#### One-to-One Association
````java
public class Person {
    private Passport passport;  // One person has exactly one passport
    
    public Person() {}
    
    public void setPassport(Passport passport) {
        this.passport = passport;
    }
    
    public Passport getPassport() {
        return passport;
    }
}

public class Passport {
    private Person owner;  // One passport belongs to exactly one person
    private String passportNumber;
    
    public Passport(String passportNumber) {
        this.passportNumber = passportNumber;
    }
    
    public void setOwner(Person person) {
        this.owner = person;
    }
}
````
#### One-to-Many Association
````java
public class Department {
    private String name;
    private List<Employee> employees;  // One department has many employees
    
    public Department(String name) {
        this.name = name;
        this.employees = new ArrayList<>();
    }
    
    public void addEmployee(Employee employee) {
        employees.add(employee);
    }
    
    public List<Employee> getEmployees() {
        return new ArrayList<>(employees);  // Return copy for encapsulation
    }
}

public class Employee {
    private String name;
    private Department department;  // One employee belongs to one department
    
    public Employee(String name) {
        this.name = name;
    }
    
    public void setDepartment(Department department) {
        this.department = department;
    }
}
````
#### Many-to-Many Association
````java
public class Student {
    private String name;
    private List<Course> courses;  // One student can enroll in many courses
    
    public Student(String name) {
        this.name = name;
        this.courses = new ArrayList<>();
    }
    
    public void enrollInCourse(Course course) {
        if (!courses.contains(course)) {
            courses.add(course);
            course.addStudent(this);
        }
    }
    
    public List<Course> getCourses() {
        return new ArrayList<>(courses);
    }
}

public class Course {
    private String courseName;
    private List<Student> students;  // One course can have many students
    
    public Course(String courseName) {
        this.courseName = courseName;
        this.students = new ArrayList<>();
    }
    
    public void addStudent(Student student) {
        if (!students.contains(student)) {
            students.add(student);
        }
    }
    
    public List<Student> getStudents() {
        return new ArrayList<>(students);
    }
}

// Usage Example
public class Main {
    public static void main(String[] args) {
        // Creating courses
        Course java = new Course("Java Programming");
        Course python = new Course("Python Programming");
        
        // Creating students
        Student alice = new Student("Alice");
        Student bob = new Student("Bob");
        
        // Enrolling students in multiple courses
        alice.enrollInCourse(java);
        alice.enrollInCourse(python);
        bob.enrollInCourse(java);
        
        // Now:
        // - Alice is enrolled in both Java and Python courses
        // - Bob is enrolled in Java course
        // - Java course has two students (Alice and Bob)
        // - Python course has one student (Alice)
    }
}
````
#### Key Points About Associations
##### 1. **One-to-One** 🔗 
- Each object is related to exactly one instance of another object
- Example: Person-Passport relationship
- Use when: representing unique pairings
##### 2. **One-to-Many** 📦
- One object can be related to multiple instances of another object
- Example: Department-Employee relationship
- Use when: representing hierarchical relationships
##### 3. Many-to-Many 🔄
- Multiple objects can be related to multiple instances of another object
- Example: Student-Course relationship
- Use when: representing complex relationships where both sides can have multiple connections

### 💡 Best Practices
- ✅ Always protect collections using defensive copying
- ✅ Consider using bi-directional relationships when necessary
- ✅ Implement proper encapsulation for associated objects
- ⚠️ Be careful with circular references in bi-directional relationships
- 🔒 Use appropriate access modifiers
- 📝 Document the nature of the relationship
### When to Use Each Type
Choose the appropriate association type based on your business requirements:

- One-to-One: for unique pairings (Person-Passport)
- One-to-Many: For hierarchical relationships (Department-Employees)
- Many-to-Many: For complex relationships requiring multiple connections (Students-Courses)
#### 📦 Aggregation (Has-A)
- Special form of association
- Represents ownership
- Objects can exist independently
#### When to Use Aggregation
- When one class "has" another class
- When child objects can exist independently
- When sharing objects across owners
````java
public class Department {
    private List<Professor> professors;  // Aggregation
}
````
#### 🧩 Composition (Part-Of)
- Stronger form of of aggregation
- Child objects cannot exist without parent
- Represents a "part-of" relationship
#### When to Use Composition
- When child objects are essential parts of parent
- When child objects shouldn't exist independently
- When enforcing tight coupling is desired
````java
public class Car {
    private final Engine engine;  // Composition
    
    public Car() {
        engine = new Engine();  // Engine cannot exist without Car
    }
}
````
### 💡 Best Practices
#### 1. Class Design
- Keep classes focused (Single Responsibility Principle)
- Favor composition over inheritance
- Use meaningful names
- Keep inheritance hierarchies shallow
#### 2. Encapsulation
- Make fields private unless there's a good reason not to
- Provide getters/setters only when necessary
- Validate data in setters
- Use immutable objects when possible
#### 3. Code Organization
- Group related classes in packages
- Maintain clear separation of concerns
- Document public APIs and complex logic
- Follow consistent naming conventions
## References
[Object Oriented Programming Notes](https://drive.google.com/file/d/1tj-HtdPZGs-XS0BvCb50f9Fjr9aVyBBd/view?usp=share_link)
[OOP Principles Playlist](https://youtube.com/playlist?list=PLxuuH5GnCIlcGnesYMkGQOqokyI2Fwu3g&si=-ExJ6GzRu8ThQiPN)

