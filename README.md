# 3-Tier-web-application-Student-Attendance-System-
Building a 3-tier web application from scratch with complete backend and frontend 

Same process as first project 

1. Architchture :

                  
                    USER
                     │
                     ▼
                  React Ui 
                     │
                     ▼
                 Spring Boot REST API   
                     │
                     ▼
                  Hibernate / JPA 
                     │
                     ▼
                 MariaDB (AWS RDS) 



2. Full Infrastructure Architecture :


                    USER
                     │
                     ▼
               Web Browser
                     │
                     │ HTTP
                     ▼
             Public EC2 IP
            (51.xx.xx.xx)
                     │
        ┌────────────┴────────────┐
        │                         │
        ▼                         ▼ 
       React Frontend             Spring Boot API
       (Attendance Dashboard)       Port 8080
       Student UI
       Teacher UI
        │
        │ REST API
        ▼
        Spring Controllers
        │
        ▼
        Service Layer
        │
        ▼
        JPA Repository
        │
        ▼
        Hibernate ORM
        │
        ▼
        MariaDB (AWS RDS)
        │
        ▼
        Attendance Tables
        Student Tables 

3. Backend Internel Architecture :

       backend/
       |
       |-controller/
       StudentController
       AttendanceController
       ClassStatsController
       |
       |-model/
       Student.java
       Attendance.java
       |
       |-repository/
       StudentRepository
       AttendanceRepository
       |
       └──resources/
        application.properties

4. Frontend Architecture :

   
       frontend/
        │
        ├── src/
        │     main.jsx
        │     index.css
        │
        ├── components (future)
        │     StudentTable
        │     Dashboard
        │     Login
        │
        └── build/
              dist/

 5. Security Layer (current) :
NOTE : This feature and more other features are in production and will update soon

Teacher access → full control

Student access → read only

6. Deployment Architecture : 

       AWS Cloud
       │
       ├── EC2
       │    ├── React Frontend
       │    └── Spring Boot Backend
       │
       └── RDS
          └── MariaDB Database



7. Process Of Creation :

  1. Overview :

  Project: Batch 5 Attendance System
  Architecture: 3-Tier Web Application

  Frontend: React (UI)
  Backend: Spring Boot (Java REST API)
  Database: AWS RDS MariaDB
  Infrastructure: AWS EC2 (Ubuntu)

2. Necessary Directories :
   Database Creation
   Backend : Spring Boot API
   Frontend : React UI
   
   1) Database Creation :
       mysql -h RDS-ENDPOINT -u admin -p
       CREATE DATABASE attendance;
       spring.jpa.hibernate.ddl-auto=update
       student
       attendance
      
   2) Backend Structure :
      AttendanceApp/backend
      Created Maven project structure:

           backend
            ├ pom.xml
            └ src
               └ main
                  ├ java
                  │   └ com
                  │       └ attendance
                  │            └ app
                  │               ├ controller
                  │               ├ model
                  │               ├ repository
                  │               └ service
                  └ resources
                  └ application.properties      

   pom.xml : Backend build file defines project dependencies contaions : spring boot, JPA, MariaDB Driver it will used by mvn clean packege. Which will give the output of : target/attendance-backend.jar


3. Frontend Structure :
     AttendanceApp/frontend

    frontend
    └ attendance-frontend
      ├ src
      │  ├ main.jsx
      │  └ index.css
      ├ package.json
      └ vite.config.js
      
main.jsx (UI LOGIC)
Responsibilities:
1) React app entry
2) API calls
3) UI rendering
   Main Logic:
   fetch(API/students)
   POST(API/students)
   DELETE(API/students/{id})

Implemented Features :
. add student
. delete student
. attendance toggle
. weekly attendance
. percentage calculation
. perform.ance score

 Ui Features : 
 Teaches Panel : Name, Batch, Course
 Student Control : Add Student, Remove Student
 Attendance Table : Weekes
 Analytics : Attendence %, Performance Score


 8. After Deployment :

        UI action
        ↓
        React API call
        ↓
        Spring Controller
        ↓
        Repository
        ↓
        Hibernate ORM
        ↓
        MariaDB database

Example: Mark attendance

UI → POST /attendance
Controller → save()
Repository → SQL insert
Database → attendance table  

9. Debugging : 



   
