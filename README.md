# 🎬 MovieShark – Smart Movie Ticket Booking System

![Spring Boot](https://img.shields.io/badge/Spring%20Boot-Backend-green?style=for-the-badge&logo=springboot)
![Java](https://img.shields.io/badge/Java-17+-orange?style=for-the-badge&logo=java)
![Kafka](https://img.shields.io/badge/Apache%20Kafka-Event%20Driven-black?style=for-the-badge&logo=apachekafka)
![MySQL](https://img.shields.io/badge/MySQL-Database-blue?style=for-the-badge&logo=mysql)
![Maven](https://img.shields.io/badge/Maven-Build-red?style=for-the-badge&logo=apachemaven)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

---

## 🚀 Overview

🎥 **MovieShark** is a scalable backend system for a movie ticket booking platform built using **Spring Boot, Kafka, and MySQL**.

It follows **event-driven architecture** and clean layered design.

---

## ⚡ Key Highlights

- ✔ Microservice-ready architecture
- ✔ Event-driven system using Kafka
- ✔ Asynchronous notifications
- ✔ RESTful APIs
- ✔ Clean DTO-based design

---

## 🏗 Architecture

```text
Client
  ↓
Controller Layer
  ↓
Service Layer
  ↓
Repository Layer
  ↓
Database (MySQL)

Service Layer → Kafka → Notification Consumer → Email Service
```

## 📁 Project Structure
```text
MovieShark
│
├── config          (Kafka, Mail, Security)
├── controller      (REST APIs)
├── service         (Business Logic)
├── repository      (DB Access)
├── domain          (Entities)
├── resource        (DTOs)
├── consumer        (Kafka Listener)
├── enums           (Constants)
├── exception       (Error Handling)
```

## ✨ Features
### 👤 User Management
- Signup user
- Fetch user details
### 🎬 Movie Management
- Add movies
- Search movies
### 🎞 Show Management
- Add shows
- Search shows by city/movie/theater
### 🏢 Theater Management
- Add theaters
- Get theater details
### 🎟 Ticket System
- Book tickets
- Fetch ticket details
### ⭐ Review System
- Add reviews
- Fetch reviews
### 🔔 Notification System (Kafka)
- Ticket booking event triggers Kafka
- Consumer sends email notification
  
  ##📡 API Endpoints
👤 User APIs

POST /user/signup
GET  /user/{id}

🎬 Movie APIs

POST /movie/add
GET  /movie/{id}
GET  /movie/title?title=Avengers

⭐ Review APIs
POST /review/add
GET  /review/find?reviewId=1
🎞 Show APIs
POST /show/add
GET  /show/search?city=&movieName=&theaterName=
🏢 Theater APIs
POST /theater/add
GET  /theater/{id}
🎟 Ticket APIs
POST /ticket/book
GET  /ticket/{id}
🔄 Kafka Flow
User books ticket
      ↓
TicketService
      ↓
Kafka Topic: TICKET_BOOKED
      ↓
NotificationConsumer
      ↓
NotificationService
      ↓
Email sent to user 📧
📧 Email Notification
Uses Gmail SMTP
Sends booking confirmation email
Secure TLS connection enabled
🧠 System Design Concepts
Layered Architecture
DTO Pattern (Resource Layer)
Event-Driven Architecture
Loose Coupling using Kafka
Scalable backend design
⚙️ How to Run
git clone <repo-url>
cd MovieShark
mvn clean install
mvn spring-boot:run
🧪 Requirements
Java 17+
MySQL
Kafka (localhost:9092)
Maven
🚀 Future Improvements
JWT Authentication
Payment Gateway Integration
Seat Locking System
Microservices decomposition
Docker Deployment
👨‍💻 Author

Kartick Sau
💻 Java Backend Developer
🔗 GitHub: KArtickCode
🔗 LinkedIn: Kartick Sau

⭐ Support

If you like this project:
⭐ Star the repo
🍴 Fork it
