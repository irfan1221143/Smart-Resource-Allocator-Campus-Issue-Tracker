# 🏫 CampusFix - Campus Complaint Management System

> A console-based Java application for reporting, routing, tracking, and resolving campus complaints.

CampusFix provides a structured way to manage issues such as **Wi-Fi outages, electrical faults, hostel maintenance, damaged furniture, and broken equipment**.

---

## 📌 Features

- 📝 Complaint creation with validation
- 🆔 Automatic unique complaint ID generation
- 🗂️ Complaint categorisation and priority
- 🏢 Department and staff assignment
- 🔄 Controlled complaint status lifecycle
- 📜 Complete complaint status history
- 🛠️ Complaint resolution with remarks
- ⭐ Post-resolution feedback
- 👥 Role-based access for Students, Staff, and Admins
- 📊 Admin analytics
- 💾 CSV backups and text reports
- 🔐 Audit logging
- 🧵 Thread-safe concurrent complaint submission demo

---

## 🔄 Complaint Workflow

```text
Submit
  ↓
Validate
  ↓
Categorise
  ↓
Assign Department & Staff
  ↓
In Progress
  ↓
Resolve
  ↓
Close
  ↓
Feedback
```

---

## 👥 User Roles

|Role	             | Capabilities                                                                   |
| ---------------- | ------------------------------------------------------------------------------ |
|🎓 Student	       | Submit, track, view history, cancel eligible complaints, give feedback         |
|👨‍🔧 Staff	         | View assigned complaints, accept, hold/resume, resolve, add remarks            |
|👨‍💼 Admin	         | View all complaints, assign staff, manage priority, analytics, reports, backups|

---

## 🛠️ Tech Stack

| Technology	               | Usage                 | 
| -------------------------- | --------------------- |
| ☕ Java 17+	               | Application           | 
| 🗄️ MySQL 8	               | Database              | 
| 🔌 JDBC	                   | Database connectivity | 
| 📦 Maven	                 | Build & dependencies  | 
| 📁 Java NIO.2	File         | handling              | 
| 🧵 ExecutorService	       | Concurrency           |

No external frameworks — plain Java, JDBC, console I/O, and NIO.2.
---
## 📂 Project Structure
```text
CampusFix/  
├── src/main/java/com/campusfix/  
│   ├── model/          # User, Student, Staff, Admin, Complaint  
│   ├── service/        # Business logic  
│   ├── dao/            # JDBC data access  
│   ├── exception/      # Custom exceptions  
│   ├── util/           # DB, validation, logging, reports, ID generation  
│   ├── concurrency/    # Concurrent submission demo  
│   └── Main.java       # Entry point  
│  
├── database/  
│   └── campusfix.sql  
├── data/  
│   ├── audit.log  
│   ├── complaints_backup.csv  
│   └── reports/  
├── pom.xml  
├── statement.md  
└── README.md  
```
---
## ⚙️ Setup
### 1. Prerequisites
  
Install:  
- JDK 17+
- Maven 3.6+
- MySQL 8
- Check installations:
- java -version
- mvn -version
- mysql --version  
  
### 2. Database Setup

From the project root:  
mysql -u root -p < database/campusfix.sql  
  
### 3. Demo Accounts
  
| Role    | Email                    | Password   |
| ------- | ------------------------ | ---------- |
| Admin   | `admin@campusfix.edu`    | `admin123` |
| Student | `aditi@campusfix.edu`    | `pass123`  |
| Student | `rohan@campusfix.edu`    | `pass123`  |
| Student | `meera@campusfix.edu`    | `pass123`  |
| Staff   | `staff102@campusfix.edu` | `staff123` |
| Staff   | `staff201@campusfix.edu` | `staff123` |
| Staff   | `staff301@campusfix.edu` | `staff123` |
  
### 4. Database Configuration
  
#### Linux / macOS
  
- export CAMPUSFIX_DB_URL="jdbc:mysql://localhost:3306/campusfix?useSSL=false&serverTimezone=UTC"
- export CAMPUSFIX_DB_USER="root"
- export CAMPUSFIX_DB_PASSWORD="your_mysql_password"  
  
#### Windows PowerShell
  
- $env:CAMPUSFIX_DB_URL = "jdbc:mysql://localhost:3306/campusfix?useSSL=false&serverTimezone=UTC"
- $env:CAMPUSFIX_DB_USER = "root"
- $env:CAMPUSFIX_DB_PASSWORD = "your_mysql_password"  
  
### 5. Build & Run
  
Maven  
mvn clean package 
java -jar target/campusfix.jar  
  
For development:  
mvn compile exec:java  

---

## 🖥️ Example Workflow
### Student
```text
Login
 ↓
Submit Wi-Fi Complaint
 ↓
Receive CMP-2026-00001
 ↓
Track Complaint
 ↓
View Resolution
 ↓
Give Feedback
```

### Admin
```text
Login
 ↓
View Complaint
 ↓
Auto/Manual Department Assignment
 ↓
Assign Staff
 ↓
Manage Priority
 ↓
View Analytics / Reports
```

### Staff
```text
Login
 ↓
View Assigned Complaint
 ↓
Accept
 ↓
IN_PROGRESS
 ↓
Resolve
 ↓
Add Resolution Remark
```

---

## 🔄 Status Lifecycle
```text
SUBMITTED
    ↓
VALIDATED
    ↓
ASSIGNED
    ↓
IN_PROGRESS
    ↓
RESOLVED
    ↓
CLOSED
```
---

## 📊 Admin Analytics
CampusFix provides:
- Total complaints
- Complaints by status
- Complaints by category
- Complaints by priority
- Resolution rate
- Average resolution time
Reports can be generated as text files and complaint data can be backed up as CSV.

---

## 🧵 Concurrency
CampusFix includes a concurrency demonstration using Java's ExecutorService.  
Multiple complaints can be submitted concurrently while maintaining thread-safe complaint ID generation.

---

## 🧪 Testing
The application handles common invalid scenarios including:
- Empty title or description
- Invalid category
- Missing complaint ID
- Unauthorized operations
- Invalid status transitions
- Feedback before resolution
- Duplicate submissions
Custom exceptions are used to handle these cases cleanly.

---

## 📚 Java Concepts Demonstrated
- Object-Oriented Programming
- Encapsulation
- Inheritance
- Polymorphism
- Abstraction
- Interfaces
- Exception Handling
- Collections
- Enums
- JDBC
- MySQL
- Java NIO.2
- Date & Time API
- Multithreading
- ExecutorService
- DAO Pattern
- Service Layer
- Input Validation
- Role-Based Access Control
- Logging
- File Handling

---
