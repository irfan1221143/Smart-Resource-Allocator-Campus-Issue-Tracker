# 🏫 CampusFix

> **A Campus Complaint Management System**

---

## 📌 Project Statement

CampusFix is a **Campus Complaint Management System** designed to provide a structured and transparent way for students and staff to report, track, manage, and resolve campus-related issues.

It replaces informal complaint methods such as chat groups or in-person reports with a centralized system where every complaint receives a unique ID and can be tracked throughout its entire lifecycle.

---

## 📝 Problem Statement

Campus issues such as:

- 📶 Broken Wi-Fi
- ⚡ Electrical faults
- 🛠️ Hostel maintenance problems
- 🪑 Damaged furniture
- 🚰 Plumbing issues
- 🏫 Other campus-related problems

are often reported informally through chat groups or directly to staff.

This creates several problems:

- ❌ Complaints do not receive a unique ID.
- ❌ There is no proper tracking mechanism.
- ❌ Complaints can easily get lost or forgotten.
- ❌ Students may not know the current status of their complaint.
- ❌ There is no complete history of actions taken.
- ❌ Administrators have limited visibility into recurring issues.
- ❌ Measuring department performance and resolution time becomes difficult.

### 💡 Solution

**CampusFix** provides a centralized complaint management system where every complaint can be:

> **Submitted → Validated → Categorised → Assigned → Tracked → Resolved → Closed**

This creates a transparent and organized workflow for handling campus issues.

---

## 🎯 Scope

CampusFix covers the **complete lifecycle of a complaint**, including:

1. 📝 Complaint submission
2. ✅ Complaint validation
3. 🗂️ Complaint categorisation
4. 🏢 Department assignment
5. 👨‍🔧 Staff assignment
6. 🔄 Status tracking
7. 📜 Complete complaint history
8. 🛠️ Complaint resolution
9. 💬 Resolution remarks
10. ⭐ Post-resolution feedback
11. 📊 Basic administrative analytics
12. 💾 CSV backups
13. 📄 Text report generation
14. 🔍 Audit logging

### 🚫 Out of Scope

The current version does **not** include:

- 📱 Dedicated mobile application
- 📧 Real SMS/Email delivery
- 🏫 University ERP integration

These features are planned as **future enhancements**.

---

## 👥 Target Users

| User | Responsibilities |
|------|------------------|
| 🎓 **Students / Staff** | Report campus issues and track complaints |
| 👨‍🔧 **Maintenance / Department Staff** | Handle assigned complaints and resolve issues |
| 👨‍💼 **Administrators** | Route complaints, assign staff, monitor progress, and view analytics |

---

## 🚀 High-Level Features

### 📝 1. Complaint Creation

- Create a new complaint.
- Validate complaint details.
- Automatically generate a unique complaint ID.
- Record complaint information and priority.

---

### 🔍 2. Complaint Tracking

- Track complaints using their unique ID.
- View the current complaint status.
- Maintain a complete status history.
- Monitor the complaint from submission to closure.

---

### 🏢 3. Department & Staff Assignment

Complaints can be assigned to the appropriate department and staff member.

Assignment can happen through:

- 🤖 Automatic assignment based on complaint category
- 👨‍💼 Manual assignment by an administrator

---

### 🔄 4. Controlled Status Lifecycle

CampusFix follows a controlled complaint status lifecycle.

Invalid status transitions are rejected to ensure that complaints follow the correct workflow.

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
