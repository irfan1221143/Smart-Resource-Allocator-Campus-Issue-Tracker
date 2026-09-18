# 🏫 CampusFix - Campus Complaint Management System

> A console-based Java application for reporting, routing, tracking, and resolving campus complaints.

CampusFix provides a structured way to manage issues such as **Wi-Fi outages, electrical faults, hostel maintenance, damaged furniture, and broken equipment**.

---

## Problem Statement

Managing campus complaints through manual or unorganized methods can lead to delays, poor tracking, unclear responsibility, and difficulty in monitoring complaint resolution. Students may face challenges in reporting issues, tracking their progress, and receiving timely updates.

**CampusFix – Campus Complaint Management System** is designed to provide a centralized system for registering, assigning, tracking, resolving, and monitoring campus complaints efficiently.

---

# Objectives

- To provide a centralized platform for managing campus complaints.
- To allow students to easily submit and track complaints.
- To automatically categorize and assign complaints to the appropriate staff or department.
- To maintain a clear complaint status and complete status history.
- To enable staff to manage and resolve assigned complaints.
- To provide administrators with analytics and reports.
- To implement role-based access for Students, Staff, and Admins.
- To maintain reliable records through database storage, audit logging, and backup.
- To demonstrate practical application of Java, MySQL, JDBC, OOP, exception handling, file handling, and concurrency concepts.

---

## Functional Requirements

These are the specific features and capabilities provided by the **CampusFix – Campus Complaint Management System**.

### 1. User & Complaint Management

- **Input:** User credentials, complaint title, description, category, and priority.
- **Process:** Authenticate users, validate complaint details, generate a unique complaint ID, and register the complaint.
- **Output:** Successfully registered complaint with a unique complaint ID.

### 2. Complaint Assignment & Tracking

- **Input:** Complaint ID, department/staff details, and status updates.
- **Process:** Assign complaints to appropriate staff or departments and manage the complaint lifecycle.
- **Output:** Updated complaint status, assignment details, and status history.

### 3. Resolution & Feedback

- **Input:** Resolution remarks and student feedback.
- **Process:** Staff resolve assigned complaints, update resolution details, and collect feedback after resolution.
- **Output:** Resolved/closed complaint with resolution remarks and feedback.

### 4. Administration & Reporting

- **Input:** Complaint and system data.
- **Process:** Admin manages complaints, assignments, users, and generates analytical reports.
- **Output:** Complaint statistics, resolution rate, average resolution time, and reports.

---

## Non-Functional Requirements

The CampusFix system shall satisfy the following non-functional requirements to ensure reliable, secure, efficient, and maintainable operation.

### 1. Performance

- The system shall process user requests with minimal delay.
- Database operations shall be optimized for efficient complaint retrieval and updates.
- The system shall support multiple complaint operations without significant performance degradation.

### 2. Security

- The system shall provide role-based access for **Student, Staff, and Admin**.
- Users shall only access operations permitted for their roles.
- Authentication shall be required before accessing protected features.
- Unauthorized complaint updates and status changes shall be rejected.

### 3. Usability

- The system shall provide a simple and user-friendly console interface.
- Clear menus and prompts shall guide users through each operation.
- Error messages shall be understandable and actionable.

### 4. Reliability

- The system shall maintain complaint data consistently.
- Invalid operations shall not corrupt existing data.
- Complaint status history and important activities shall be preserved.

### 5. Scalability

- The system shall support an increasing number of users and complaints.
- The database-based architecture shall allow the system to handle larger datasets.
- The modular design shall allow additional features to be added in the future.

---

## System Architecture Diagram

```text
                         ┌──────────────────────┐
                         │       Users          │
                         │ Student | Staff      │
                         │        | Admin       │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │    Console UI        │
                         │   Input / Output     │
                         └──────────┬───────────┘
                                    │
                                    ▼
                    ┌──────────────────────────────┐
                    │       Service Layer          │
                    │                              │
                    │ Authentication | Complaints  │
                    │ Assignment | Resolution     │
                    │ Feedback | Analytics          │
                    └──────────────┬───────────────┘
                                   │
                    ┌──────────────┴───────────────┐
                    ▼                              ▼
          ┌──────────────────┐           ┌──────────────────┐
          │    DAO Layer     │           │ Utility /        │
          │                  │           │ Exception Layer  │
          │ Student DAO      │           │ Validation       │
          │ Complaint DAO    │           │ Logging          │
          │ Staff DAO        │           │ File Handling    │
          └────────┬─────────┘           └──────────────────┘
                   │
                   ▼
          ┌──────────────────┐
          │   JDBC Layer     │
          │ MySQL Connector  │
          └────────┬─────────┘
                   │
                   ▼
          ┌──────────────────┐
          │    MySQL DB      │
          │                  │
          │ Users            │
          │ Complaints       │
          │ Assignments      │
          │ Status History   │
          │ Feedback         │
          └──────────────────┘

                   ┌──────────────────────┐
                   │   File System        │
                   │                      │
                   │ Audit Logs           │
                   │ CSV Backup           │
                   │ Analytics Reports    │
                   └──────────────────────┘
```
## System Workflow

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

## Computation / ML Requirements

Not Applicable.  

CampusFix is a Java-based campus complaint management system that focuses on software architecture, database management, object-oriented programming, validation, exception handling, file handling, and concurrency rather than machine learning or computational modeling.
  
Therefore, the following requirements are not applicable:
- Dataset Description
- Model Selection Rationale
- Model Evaluation Methodology

---

## Author
Irfan Alam Ansari
25BAI11088
B.tech in CSE (AI&ML)
