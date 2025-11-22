# **Campus Course & Records Manager (CCRM)**

### **A Java-Powered Console Application for Academic Administration**

CCRM is an enterprise-grade, command-line interface (CLI) application designed for the comprehensive management of an academic institution's core data. Built with Java SE and utilizing an Oracle database backend, this system provides administrators with a powerful and efficient tool for handling student records, course catalogs, and enrollment data through a streamlined, text-based interface.

## **System Capabilities**

CCRM is organized around several key administrative functions, providing a full suite of tools for managing the academic environment.

#### **Academic & Student Affairs**

* **Student Lifecycle Tracking**: Manage the complete student journey, from initial registration and personal details to updating academic standing and graduation status.  
* **Curriculum & Course Catalog Management**: Define, modify, and list all courses offered by the institution. Assign faculty members to specific courses and semesters with ease.  
* **Intelligent Enrollment Processing**: Handle student course registrations and withdrawals while automatically enforcing institutional policies, such as maximum credit limits per semester.

#### **Data & Operations**

* **Academic Reporting**: Generate detailed academic transcripts for any student, providing a complete record of their coursework and grades.  
* **Data Migration & Archiving**: Facilitates seamless data handling with utilities for importing and exporting records via CSV files.  
* **System Backup & Recovery**: Create compressed, timestamped .zip archives of the entire database, ensuring data integrity and providing a robust disaster recovery solution.

## **Under the Hood: Technology & Design**

This project serves as a practical implementation of key software engineering principles and Java technologies.

| Area | Implementation & Rationale |
| :---- | :---- |
| **Object-Oriented Architecture** | The domain model (e.g., Person, Student) is built upon the core OOP principles of **Encapsulation, Inheritance, Polymorphism, and Abstraction** to create a logical and maintainable structure. |
| **High-Performance File I/O** | The java.nio.file package (**NIO.2**) is utilized in the ImportExportService and BackupService for efficient, non-blocking file operations, which is critical for handling large datasets. |
| **Persistent Data Storage** | **JDBC** provides the vital link to the Oracle database, enabling robust and reliable data persistence for all application entities. |
| **Functional Programming in Java** | **Lambda Expressions and the Stream API** are used within the CourseService to implement clean, declarative, and highly efficient data filtering logic. |
| **Creational Design Patterns** | The project employs the **Singleton Pattern** (AppConfig) to guarantee a single, globally accessible configuration state, and the **Builder Pattern** (Course) to ensure the safe and readable construction of complex objects. |
| **Robust Error Handling** | A custom exception hierarchy (e.g., MaxCreditLimitExceededException) allows the application to handle specific operational errors gracefully and provide meaningful feedback to the user. |

## **Deployment & Execution Guide**

Follow these steps to compile and run the application.

#### **1\. System Requirements**

* **Java Development Kit (JDK)**: Version 11 or a more recent release.  
* **Oracle Database**: A running instance of Oracle Database that is accessible from the machine running the application.

#### **2\. Initial Database Configuration**

A one-time setup is required to create the database user. Connect to your Oracle instance with administrative privileges and execute the following SQL script:

CREATE USER ccrm\_user IDENTIFIED BY ccrm\_pass;  
GRANT CONNECT, RESOURCE, DBA TO ccrm\_user;

*The application is designed to auto-generate the necessary table schema upon its first launch.*

#### **3\. Compiling the Source Code**

Navigate to the project's root directory in your terminal and compile the application using this command:

javac \-d bin \-cp "lib/ojdbc17.jar" src/edu/ccrm/cli/\*.java src/edu/ccrm/config/\*.java src/edu/ccrm/domain/\*.java src/edu/ccrm/exception/\*.java src/edu/ccrm/io/\*.java src/edu/ccrm/service/\*.java src/edu/ccrm/util/\*.java

#### **4\. Running the Application**

Once compiled, launch the CCRM application with the following command:

java \-cp "bin;lib/ojdbc17.jar" edu.ccrm.cli.Main

For development and debugging, you can enable assertions by adding the \-ea flag:

java \-ea \-cp "bin;lib/ojdbc17.jar" edu.ccrm.cli.Main

## **The Java Platform: A Brief Overview**

An understanding of the Java ecosystem is helpful for context.

| Acronym | Stands For | Role & Responsibility |
| :---- | :---- | :---- |
| **JVM** | Java Virtual Machine | The execution engine that interprets compiled Java bytecode and runs it on the underlying operating system. It's the component that makes Java "write once, run anywhere." |
| **JRE** | Java Runtime Environment | The software package that provides the JVM and the necessary libraries to **run** a compiled Java application. |
| **JDK** | Java Development Kit | The complete software development kit for Java programmers. It includes the JRE, a compiler (javac), a debugger, and other essential tools for **developing** applications. |

**Developed by Vanshika Chaudhary**

*This project was created as part of the "Programming in Java" course on the Vityarthi portal.*
