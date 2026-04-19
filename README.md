# 📔 AI-Powered Journal Management System

A production-ready backend system built with Spring Boot that combines secure authentication, AI-powered sentiment analysis, and asynchronous event processing.

## 🚀 Overview

Backend API running on localhost:8080
Swagger UI: http://localhost:8080/swagger-ui.html

## 🛠 Tech Stack

Backend: Java, Spring Boot 3
Security: JWT, Spring Security
Database: PostgreSQL
Caching: Redis
Messaging: Apache Kafka
AI: OpenAI API
Email: Brevo SMTP
API Docs: Swagger / OpenAPI

## ✨ Features

🔐 JWT Authentication with role-based access
🤖 AI Sentiment Analysis (HAPPY, SAD, ANGRY, ANXIOUS, PEACEFUL, BORED, TIRED)
⚡ Kafka-based asynchronous processing
📧 Email notifications after journal analysis
🚀 Redis caching for performance optimization
📊 Swagger API documentation

## 🧠 Architecture

User → REST API → Kafka Producer → Kafka Consumer → Sentiment Analysis → Database → Email Notification

## 📁 Project Structure

src/main/java/com/springYT/journalappBackend/

controller/ — REST API endpoints
service/ — Business logic
entity/ — Database models
repository/ — Data access layer
config/ — Security, Kafka, Redis config
filter/ — JWT filter
enums/ — Sentiment enum
utils/ — JWT utilities

## 🔌 API Endpoints

Public APIs
POST /public/signup — Register user
POST /public/login — Login and get JWT
GET /public/health-check — Health check

Journal APIs (JWT required)
GET /journal — Get all entries
POST /journal — Create entry
GET /journal/id/{id} — Get by ID
PUT /journal/id/{id} — Update
DELETE /journal/id/{id} — Delete

Admin APIs (ADMIN role)
GET /admin/all-user — Get all users
POST /admin/create-admin-user — Create admin

## ⚙️ Setup & Installation

Prerequisites
Java 21
PostgreSQL
Redis
Docker (for Kafka)

1. Clone repository
   git clone https://github.com/AKASH7577/Journal-Appplication.git
   cd User-management-Appplication

2. Start Kafka (Docker)
   docker run -d --name kafka -p 9092:9092 apache/kafka

3. Configure application.yml

spring:
datasource:
url: jdbc:postgresql://localhost:5432/journaldb
username: your_username
password: your_password

mail:
host: smtp-relay.brevo.com
port: 587
username: YOUR_BREVO_EMAIL
password: YOUR_SMTP_KEY
properties:
mail.smtp.auth: true
mail.smtp.starttls.enable: true

kafka:
bootstrap-servers: localhost:9092

openai:
api:
key: YOUR_OPENAI_KEY

4. Run application
   mvn spring-boot:run

5. Open Swagger
   http://localhost:8080/swagger-ui.html

## 🧪 Testing (Postman)

Signup
POST /public/signup

Login
POST /public/login

Create Journal Entry
POST /journal
Header: Authorization: Bearer YOUR_TOKEN

{
"title": "My Day",
"content": "I am feeling very happy today"
}

Expected Result
Entry saved in database
Sentiment detected
Email sent to user

## 📈 Highlights

Handles concurrent requests
Improved response time using Redis
Scalable architecture using Kafka

## 🔮 Future Improvements

Weekly sentiment reports
Analytics dashboard
Mobile app integration
Docker deployment
Cloud deployment

## 👨‍💻 Author

Akash Shinde
GitHub: https://github.com/AKASH7577
LinkedIn: https://www.linkedin.com/in/akash-shinde
 ## Screenshots
 <img width="1919" height="1055" alt="image" src="https://github.com/user-attachments/assets/b9aaa2cc-1d64-4c7a-95f3-d7ef1cbae5f6" /><img width="1919" height="1023" alt="image" src="https://github.com/user-attachments/assets/ec4c4034-5203-41de-9667-0471c8ea8932" />
 <img width="1320" height="747" alt="image" src="https://github.com/user-attachments/assets/66f7aad0-8962-47b1-ac6c-73df10bc7d7e" />
 <img width="1909" height="1079" alt="image" src="https://github.com/user-attachments/assets/48b789ae-5681-433b-9daf-5819bb3b7a54" />
 <img width="1766" height="861" alt="image" src="https://github.com/user-attachments/assets/1ad9f250-9f7b-4df8-975e-81e3590d45c6" />





