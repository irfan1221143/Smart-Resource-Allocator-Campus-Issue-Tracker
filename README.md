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
~~~
Role	                                Capabilities
🎓 Student	                            Submit, track, view history, cancel eligible complaints, give feedback
👨‍🔧 Staff	                            View assigned complaints, accept, hold/resume, resolve, add remarks
👨‍💼 Admin	                            View all complaints, assign staff, manage priority, analytics, reports, backups
~~~
---

## 🛠️ Tech Stack
~~~
Technology	                          Usage
☕ Java 17+	                          Application
🗄️ MySQL 8	                          Database
🔌 JDBC	                              Database connectivity
📦 Maven	                          Build & dependencies
📁 Java NIO.2	File                  handling
🧵 ExecutorService	                  Concurrency
~~~
No external frameworks — plain Java, JDBC, console I/O, and NIO.2.
