# Registration-Form

This is a simple Java-based web application that allows users to register, view, edit, and delete user information. It uses JSP, Servlets, and a MySQL database for backend functionality.

## Prerequisites

1. **Java Development Kit (JDK)**:
   - Ensure JDK 8 or later is installed.
   - [Download JDK](https://www.oracle.com/java/technologies/javase-downloads.html)

2. **Apache Tomcat Server**:
   - Install Apache Tomcat 8.5 or later.
   - [Download Tomcat](https://tomcat.apache.org/download-90.cgi)

3. **MySQL Database**:
   - Install  MySQL Workbench.
   - [Download MySQL](https://dev.mysql.com/downloads/mysql/)

4. **IDE** (Optional but recommended):
   - Use an IDE like Eclipse.

5. **Required JAR Files**:
   - Ensure the following JAR files are added to your project’s `lib` directory:
     - `jsp-api-2.2.jar`
     - `jstl-1.2.jar`
     - `mysql-connector-java-8.0.13.jar`
     - `servlet-api-2.5.jar`

---

## Database Setup

1. **Create the Database**:
   - Open MySQL Workbench or any database client.
   - Run the following commands to create the database and table:
     ```sql
     CREATE DATABASE userdb;

     USE userdb;

     CREATE TABLE users (
         id INT AUTO_INCREMENT PRIMARY KEY,
         name VARCHAR(100) NOT NULL,
         email VARCHAR(100) NOT NULL,
         dob DATE NOT NULL,
         mob INT NOT NULL
     );
     ```

2. **Configure Database Credentials**:
   - Open the `UserDAO.java` file and update the following fields with your MySQL credentials:
     ```java
     private String jdbcURL = "jdbc:mysql://localhost:3306/userdb?useSSL=false";
     private String jdbcUsername = "root";
     private String jdbcPassword = "zxcv@0987";
     ```

---
##Frontend

The frontend uses JSP pages (user-form.jsp and user-list.jsp) for user interaction.
Bootstrap 4 is included for styling.

## Backend Setup

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/LakshmiThippeRamappa/Registration-Form/tree/main
   cd Registration-Form
