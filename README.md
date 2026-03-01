# 📌 Claims Processing System

![Java](https://img.shields.io/badge/Java-11-blue)
![Spring Boot](https://img.shields.io/badge/SpringBoot-2.5.4-brightgreen)
![Kafka](https://img.shields.io/badge/Kafka-EventDriven-black)
![Redis](https://img.shields.io/badge/Redis-Cache-red)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue)
![CI/CD](https://img.shields.io/badge/CI/CD-Jenkins-orange)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

## 🏢 Client
**Statewide Insurance Group (USA)**  
*(Fictional client used for educational and demonstration purposes.)*

---

## 📖 Project Overview

The **Claims Processing System** is an enterprise-style backend application designed to manage and process insurance claims efficiently.

The system enables:

- Secure claim submission and processing
- Real-time claim status updates
- Automated validation and reporting
- Event-driven notifications
- High-performance data retrieval using caching
- Centralized logging and monitoring

The application follows a **Monolithic Architecture** while integrating modern enterprise tools such as Kafka, Redis, OAuth2, and CI/CD pipelines.

---

## 🏗️ Architecture Overview

### 🔹 Backend
- Spring Boot (Monolithic Architecture)
- RESTful APIs
- Layered design (Controller → Service → Repository → Database)

### 🔹 Database
- MySQL for persistent storage
- JPA/Hibernate for ORM

### 🔹 Caching
- Redis for storing frequently accessed data
- Used for claim status and reporting optimization

### 🔹 Messaging System
- Apache Kafka for real-time claim status updates
- Asynchronous event-driven processing

### 🔹 Security
- OAuth2 Authentication
- JWT Token-based Authorization
- Role-Based Access Control (RBAC)
- Token validation via custom filter

### 🔹 Logging & Monitoring
- Log4j2 for structured logging
- Splunk for centralized log monitoring

### 🔹 DevOps & Deployment
- Docker for containerization
- Kubernetes for orchestration
- Jenkins for CI/CD automation
- Blue-Green deployment strategy

---

## 🛠️ Tech Stack

| Layer | Technology |
|--------|------------|
| Language | Java 11 |
| Framework | Spring Boot 2.5.4 |
| Security | OAuth2 + JWT |
| Database | MySQL |
| Caching | Redis |
| Messaging | Apache Kafka |
| Logging | Log4j2 |
| Monitoring | Splunk |
| Testing | JUnit + Mockito |
| CI/CD | Jenkins |
| Containerization | Docker |
| Orchestration | Kubernetes |

---

## 🗃️ Database Schema (Major Tables)

- Claims
- Users
- Transactions
- Audit Logs
- Payment Details

Relational mapping implemented using JPA/Hibernate.

---

## 🌐 REST APIs

### Claims Management
- `POST /claims` – Submit a new claim
- `GET /claims/{claimId}` – Retrieve claim details
- `PUT /claims/{claimId}` – Update claim
- `DELETE /claims/{claimId}` – Delete claim
- `GET /claims/user/{userId}` – Get claims by user

### User Management
- `POST /users/register` – Register user
- `POST /users/login` – Authenticate and receive JWT
- `GET /users/{userId}` – Get user details
- `PUT /users/{userId}` – Update user
- `DELETE /users/{userId}` – Deactivate user

### Reporting
- `GET /reports/claims/status`
- `GET /reports/claims/summary`

### Notifications
- Kafka Topic: `claim-updates`
- Email notifications triggered on status change

---

## ⚡ Redis Caching Implementation

Redis is used to:

- Cache claim status updates
- Store frequently accessed reports
- Reduce database load during high traffic

Annotations used:
- `@Cacheable`
- `@CachePut`
- `@CacheEvict`

---

## 🔔 Kafka Integration

Kafka is used for:

- Real-time claim status updates
- Asynchronous event publishing
- Email notifications via Kafka consumer

Flow:
1. Claim status updated
2. Event published to Kafka topic
3. Consumer processes event
4. Email notification sent

---

## 🔐 Security Implementation

- OAuth2-based authentication
- JWT token validation
- Custom `JwtAuthenticationFilter`
- Role-Based Access Control
- Secured endpoints except `/login` and `/register`

---

## 🧪 Testing Strategy

- Unit Testing using JUnit
- Mocking using Mockito
- Code Coverage monitored via SonarQube
- Minimum coverage threshold: 80%

---

## 🚀 CI/CD Pipeline

1. Code pushed to Git repository
2. Jenkins triggers automated build
3. Maven builds project
4. JUnit test cases executed
5. Docker image generated
6. Kubernetes deployment
7. Blue-Green release strategy

---

## 📦 How to Run Locally

### Prerequisites
- Java 11
- Maven
- MySQL
- Redis
- Kafka

### Clone Repository

```bash
git clone https://github.com/ravichimkar/ClaimProcessingSystem.git
cd ClaimProcessingSystem
Build Project
mvn clean install
Run Application
mvn spring-boot:run

Application will start on:

http://localhost:8080
