# 3-Tier-web-application-Student-Attendance-System-
Building a 3-tier web application from scratch with complete backend and frontend 

Same process as first project 
Architechture :

User
 │
 ▼
React UI
 │
 ▼
Spring Boot REST API
 │
 ▼
Hibernate / JPA
 │
 ▼
MariaDB (AWS RDS)

Full Infrastructure Architecture :

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

   
