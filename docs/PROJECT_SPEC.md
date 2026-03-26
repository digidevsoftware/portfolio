# Employee Shift & Management System
## Version 1 Project Specification

## 1. Project Title
**Employee Shift & Management System**

---

## 2. Project Overview
The Employee Shift & Management System is a web-based application designed to make shift management easier and more efficient. The system will allow managers or administrators to manage employee records, create and assign shifts, and view work schedules through a clear web interface instead of using a terminal-based system.

This project is being developed as a practical software engineering portfolio piece to demonstrate full-stack Java development skills using Spring Boot, database integration, and web application design.

---

## 3. Purpose
The purpose of Version 1 is to provide an easier way for users to manage employee shifts.

The system should allow managers or administrators to:
- add employees
- edit employees
- delete employees
- create shifts
- edit shifts
- delete shifts
- assign employees to shifts
- view schedules

The aim is to improve usability, organisation, and efficiency compared to manually managing shifts or relying on a terminal-based interface.

---

## 4. Objectives
The main objectives of the project are:

- build a functional web-based shift management system
- provide a user-friendly interface for managers/admins
- store employee and shift data in a relational database
- demonstrate practical use of Spring Boot, Thymeleaf, and PostgreSQL
- show software engineering skills through structured design and implementation

---

## 5. Intended Users
### Primary users
- **Manager**
- **Administrator**

These users will have access to employee and shift management functions.

### Future users
- **Employee**

Employee access may be added in a later version for viewing assigned shifts, submitting availability, and requesting leave.

For Version 1, the system will focus on **manager/admin functionality only**.

---

## 6. Scope of Version 1

### Included in Version 1
- manager/admin login
- employee management
- shift management
- employee-to-shift assignment
- schedule viewing
- data validation
- database persistence

### Excluded from Version 1
- employee self-service portal
- leave request handling
- availability submission
- notifications
- payroll integration
- advanced analytics
- mobile app support
- REST API for external clients
- React frontend

These may be considered for future versions.

---

## 7. Functional Requirements

### 7.1 Authentication and Access Control
The system shall:
- allow managers/admins to log in securely
- restrict access to authorised users only
- prevent unauthenticated users from accessing management pages

### 7.2 Employee Management
The system shall allow authorised users to:
- add a new employee
- edit existing employee details
- delete an employee
- view a list of employees
- search or filter employees if implemented in V1 polish

### 7.3 Shift Management
The system shall allow authorised users to:
- create a new shift
- edit an existing shift
- delete a shift
- assign an employee to a shift
- view details of each shift

### 7.4 Schedule Viewing
The system shall allow authorised users to:
- view all shifts
- view shifts by date
- view shifts by employee
- view shifts in an organised schedule format

### 7.5 Data Validation
The system shall:
- validate required fields before saving data
- prevent invalid or incomplete form submissions
- display clear validation messages to the user

---

## 8. Non-Functional Requirements

The system should:
- be easy to use for non-technical users
- have a clean and simple interface
- be reliable in storing and retrieving data
- follow a maintainable code structure
- be scalable enough for future features
- use standard security practices for authentication
- perform well for normal small-business style usage

---

## 9. Technology Stack

### Backend
- **Java**
- **Spring Boot**

### Frontend
- **Thymeleaf**
- **HTML**
- **CSS**
- optional **Bootstrap** for styling

### Database
- **PostgreSQL**

### Data Access
- **Spring Data JPA**

### Security
- **Spring Security**

### Build Tool
- **Maven**

### Package / Naming
- **Group:** `digidevsoftware`
- **Recommended package:** `digidevsoftware.shiftmanagementsystem`

---

## 10. System Architecture
The application will follow a standard layered Spring Boot architecture:

- **Controller layer**  
  Handles HTTP requests and returns views

- **Service layer**  
  Contains business logic

- **Repository layer**  
  Handles database access using Spring Data JPA

- **Model/Entity layer**  
  Defines database entities and relationships

- **View layer**  
  Thymeleaf templates for the user interface

This structure improves maintainability and makes the application easier to extend.

---

## 11. Core Modules

### 11.1 Authentication Module
Responsible for:
- login
- access restriction
- user role handling

### 11.2 Employee Module
Responsible for:
- employee creation
- employee editing
- employee deletion
- employee listing

### 11.3 Shift Module
Responsible for:
- shift creation
- shift editing
- shift deletion
- employee assignment to shifts

### 11.4 Schedule Module
Responsible for:
- displaying schedules
- filtering shifts by date or employee
- presenting assigned shifts clearly

---

## 12. Database Design

### 12.1 User Entity
Used for authentication and authorisation.

**Fields:**
- `id`
- `username`
- `password`
- `role`

### 12.2 Employee Entity
Stores employee details.

**Fields:**
- `id`
- `firstName`
- `lastName`
- `email`
- `phone`
- `position`
- `status`

### 12.3 Shift Entity
Stores shift information.

**Fields:**
- `id`
- `date`
- `startTime`
- `endTime`
- `shiftType`
- `notes`
- `employee` *(many-to-one relationship with Employee)*

---

## 13. Entity Relationships

- One **employee** can have many **shifts**
- One **shift** is assigned to one **employee**
- One **user** represents a system login account

This means:
- **Employee → Shift** = one-to-many
- **Shift → Employee** = many-to-one

---

## 14. Main Pages / Views

### Authentication
- Login page

### Dashboard
- Manager/admin dashboard

### Employee Pages
- Employee list page
- Add employee page
- Edit employee page

### Shift Pages
- Shift list page
- Create shift page
- Edit shift page

### Schedule Pages
- Weekly or date-based schedule view
- Filter by employee/date page or controls

---

## 15. User Flow Example

A manager logs into the system and:
1. opens the employee page
2. adds employee records
3. opens the shift page
4. creates shifts
5. assigns employees to shifts
6. opens the schedule page
7. views the completed work schedule

This provides a simple and clear workflow for shift management.

---

## 16. Validation Rules

Examples of validation for Version 1:

### Employee
- first name is required
- last name is required
- email should be valid
- position is required

### Shift
- date is required
- start time is required
- end time is required
- assigned employee is required
- end time must be later than start time

### User
- username is required
- password is required

---

## 17. Security Approach
Version 1 will use **Spring Security** to provide:
- login authentication
- password protection
- restricted access to protected pages

Initially, the system can use:
- one predefined manager/admin account
- role-based restriction for management pages

More advanced user management can be added later.

---

## 18. Error Handling
The system should:
- show form validation errors clearly
- prevent saving invalid data
- handle missing records safely
- show friendly error messages where appropriate

---

## 19. Future Enhancements
Possible future improvements include:
- employee self-service login
- leave request management
- availability submission
- conflict detection for overlapping shifts
- calendar-style schedule UI
- dashboard statistics
- REST API support
- React frontend
- deployment to a cloud platform

---

## 20. Development Plan

### Phase 1 — Project Setup
- create Spring Boot project
- configure dependencies
- connect PostgreSQL database
- configure application properties

### Phase 2 — Employee Management
- create Employee entity
- create repository, service, and controller
- create Thymeleaf views for CRUD operations

### Phase 3 — Shift Management
- create Shift entity
- define relationship with Employee
- create repository, service, and controller
- create shift CRUD views

### Phase 4 — Schedule View
- create schedule page
- display shifts by date and/or employee

### Phase 5 — Authentication
- add Spring Security
- create login page
- secure routes

### Phase 6 — Testing and Polish
- validate forms
- improve styling
- add sample data
- test user flows
- prepare README and screenshots

---

## 21. Success Criteria
Version 1 will be successful if:
- managers/admins can log in
- employees can be added, edited, and deleted
- shifts can be created, edited, and deleted
- shifts can be assigned to employees
- schedules can be viewed clearly
- all data is stored in PostgreSQL
- the application runs successfully as a Spring Boot web app

---

## 22. Summary
The Employee Shift & Management System V1 will be a Spring Boot web application built to simplify shift management for managers and administrators. It will replace terminal-based interaction with a clearer web interface and demonstrate practical full-stack Java development skills through employee management, shift assignment, schedule viewing, database integration, and authentication.
