# Student Management System

A console-based **Student Management System** developed using **Java, JPA, Hibernate, Maven, and MySQL**. The project demonstrates CRUD operations and a **unidirectional many-to-many relationship** between students and subjects using JPA.

## 🚀 Features

* Add, view, update, and delete students
* Add, view, update, and delete subjects
* Assign multiple subjects to a student
* View students with their assigned subjects
* JPA-based persistence using `EntityManager`
* Hibernate as the JPA implementation
* MySQL database integration
* Layered project architecture
* Console-based user interface

## 🛠️ Technologies Used

* **Java**
* **JPA (Jakarta Persistence API)**
* **Hibernate ORM**
* **MySQL**
* **Maven**
* **Lombok**
* **Eclipse IDE**

## 🏗️ Project Structure

```text
student_management_system
│
├── src
│   └── main
│       ├── java
│       │   └── com.naresh.student_management_system
│       │       │
│       │       ├── controller
│       │       │   └── MenuController.java
│       │       │
│       │       ├── service
│       │       │   └── StudentSubjectService.java
│       │       │
│       │       ├── dao
│       │       │   └── StudentSubjectDao.java
│       │       │
│       │       ├── entity
│       │       │   ├── Student.java
│       │       │   └── Subject.java
│       │       │
│       │       └── util
│       │           └── JpaUtil.java
│       │
│       └── resources
│           └── META-INF
│               └── persistence.xml
│
├── pom.xml
├── .gitignore
└── README.md
```

## 🧱 Architecture

The project follows a simple layered architecture:

```text
Main
 │
 ▼
Controller
 │
 ▼
Service
 │
 ▼
DAO
 │
 ▼
EntityManager / JPA
 │
 ▼
Hibernate
 │
 ▼
MySQL
```

### Controller

Handles user interaction and receives input from the console.

### Service

Contains the application's business logic and coordinates operations between the controller and DAO.

### DAO

Handles database persistence operations using JPA's `EntityManager`.

### Entity

Contains the JPA entity classes representing database tables and their relationships.

### Util

Contains reusable utility classes such as `EntityManagerFactory` configuration and JPA resource management.

## 🔗 Entity Relationship

The project uses a **unidirectional many-to-many relationship** between `Student` and `Subject`.

```text
Student
   │
   │ @ManyToMany
   ▼
Subject
```

A student can have multiple subjects.

The relationship is **unidirectional**, meaning `Student` maintains the reference to `Subject`, while `Subject` does not maintain a reference back to `Student`.

## 🗄️ Database Setup

Create the database directly in MySQL:

```sql
CREATE DATABASE student_management;
```

Configure the database credentials in:

```text
src/main/resources/META-INF/persistence.xml
```

Example:

```xml
<property name="jakarta.persistence.jdbc.url"
          value="jdbc:mysql://localhost:3306/student_management"/>

<property name="jakarta.persistence.jdbc.user"
          value="root"/>

<property name="jakarta.persistence.jdbc.password"
          value="your_password"/>
```

Hibernate is configured to automatically create or update the required tables:

```xml
<property name="hibernate.hbm2ddl.auto"
          value="update"/>
```

## ▶️ How to Run

1. Clone the repository.
2. Open the project in Eclipse as a Maven project.
3. Make sure MySQL Server is running.
4. Create the `student_management` database.
5. Configure your MySQL username and password in `persistence.xml`.
6. Allow Maven to download the project dependencies.
7. Run `Main.java`.
8. Use the console menu to perform student and subject operations.

## 📚 Concepts Demonstrated

* Object-Oriented Programming
* Layered Architecture
* JPA Entity Mapping
* `@Entity`
* `@Id`
* `@ManyToMany`
* Unidirectional relationships
* `EntityManager`
* `EntityManagerFactory`
* JPA transactions
* CRUD operations
* DAO pattern
* Service layer
* Hibernate ORM
* Maven dependency management
* MySQL database connectivity

## 🎯 Purpose

This project was created as a **hands-on JPA and Hibernate practice project** to understand persistence, entity relationships, CRUD operations, and layered application architecture in Java.

## 👨‍💻 Author

**Naresh**

Java Developer | MCA Postgraduate
