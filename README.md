# Real-Time Chat Application

A high-performance, real-time chat application built with **Spring Boot**, **Thymeleaf**, **Bootstrap**, and **WebSockets (STOMP/SockJS)**. This application allows multiple users to join the same chat room instantly by simply opening the link in different browser windows.

## 🚀 Features
* **Instant Messaging:** Real-time communication powered by WebSocket STOMP protocol.
* **Multi-Window Support:** Open the application in multiple tabs to simulate a multi-user environment.
* **Single-Screen UI:** Minimalist interface for username input and live messaging.
* **Responsive Layout:** Mobile-friendly design powered by Bootstrap 5.

## 🛠️ Technologies Used
* **Backend:** Java, Spring Boot, Spring WebSockets
* **Frontend:** Thymeleaf, Bootstrap 5, SockJS-client, STOMP.js
* **Build Tool:** Maven

## 📋 Prerequisites
* **JDK:** 17 or higher
* **Build Tool:** Maven installed
* **Environment:** A modern web browser

## ⚙️ Setup & Execution

### 1. Project Dependencies
Ensure your `pom.xml` contains the WebSocket starter:
```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-websocket</artifactId>
</dependency>
