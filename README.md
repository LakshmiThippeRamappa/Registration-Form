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
**Frontend**

The frontend uses JSP pages (user-form.jsp and user-list.jsp) for user interaction.
Bootstrap 4 is included for styling.

**1. Name Field:**
Pattern: pattern="[A-Za-z\s]+"
Only allows letters (both uppercase and lowercase) and spaces.
JavaScript: oninput="this.value = this.value.replace(/[^A-Za-z\s]/g, '');"
This ensures that when the user types, any non-letter or non-space character is automatically removed.
Required: required="required"
Ensures the field must be filled out before submission.

**2. User Email Field:**
Pattern: pattern="[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}"
The email must follow a standard format, e.g., username@example.com.
Allows letters, numbers, and certain characters like _, ., %, +, and -.
Required: required="required"
The email field is mandatory.

**3. Date of Birth (DOB) Field:**
Type: type="date"
Allows the user to pick a date from a date picker (standard browser behavior).
Required: required="required"
Ensures the date of birth must be provided.

**4. Mobile Number Field:**
Pattern: pattern="\d{10}"
The input should only be 10 digits long.
Max Length: maxlength="10"
Restricts the input length to 10 characters.
Title: title="Please enter a valid 10-digit mobile number."
Provides a tooltip or message when the validation fails.
JavaScript:
onkeypress="if(event.key < '0' || event.key > '9') event.preventDefault();"
Ensures that only numbers (0-9) can be typed; prevents alphabetic or special characters.
oninput="this.value = this.value.slice(0, 10);"
Limits the mobile number input to 10 characters.

**Summary of Validation:**
Name: Only letters and spaces.
Email: Must be in a valid email format.
DOB: Must select a date.
Mobile Number: Must be exactly 10 digits, and only numeric input is allowed.

## Backend Setup

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/LakshmiThippeRamappa/Registration-Form/tree/main
   cd Registration-Form
