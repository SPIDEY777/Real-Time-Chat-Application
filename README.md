# Real-Time Chat Application

A simple real-time group chat application built using **Spring Boot**, **Thymeleaf**, **Bootstrap**, **SockJS**, and **STOMP.js**. The application allows multiple users to join the same chat room by opening the application URL in different browser windows or tabs and exchange messages instantly.

## Features

* Real-time messaging using WebSockets
* Group chat functionality
* Single-page user interface
* User name identification for messages
* Instant message broadcasting to all connected users
* Responsive UI with Bootstrap
* SockJS fallback support for browsers without native WebSocket support
* Lightweight and easy-to-understand architecture

## Technologies Used

### Backend

* Spring Boot
* Spring WebSocket
* Spring Messaging

### Frontend

* Thymeleaf
* Bootstrap 5
* JavaScript
* SockJS
* STOMP.js

## Application Overview

The application consists of a single chat screen containing:

1. **Name Field**

   * Users enter their display name before sending messages.

2. **Message Input Field**

   * Users type their chat messages.

3. **Chat Window**

   * Displays all messages sent by connected users in real time.

When a user sends a message:

1. The message is sent to the Spring Boot WebSocket endpoint.
2. The server broadcasts the message to all subscribed clients.
3. Every connected user immediately receives and sees the new message.

Since all users subscribe to the same topic, anyone accessing the application URL can participate in the conversation.

## Project Structure

```text
src
├── main
│   ├── java
│   │   └── com.example.chat
│   │       ├── config
│   │       │   └── WebSocketConfig.java
│   │       ├── controller
│   │       │   └── ChatController.java
│   │       ├── model
│   │       │   └── ChatMessage.java
│   │       └── ChatApplication.java
│   │
│   └── resources
│       ├── templates
│       │   └── chat.html
│       └── application.properties
```

## WebSocket Flow

```text
Client
   |
   |  Connect via SockJS
   v
WebSocket Endpoint (/chat)
   |
   |  STOMP Message
   v
Spring Boot Controller
   |
   |  Broadcast
   v
Topic (/topic/messages)
   |
   v
All Connected Clients
```

## Getting Started

### Prerequisites

* Java 17+ (or your project's Java version)
* Maven 3.8+
* IDE (IntelliJ IDEA, Eclipse, VS Code)

### Clone the Repository

```bash
git clone https://github.com/your-username/realtime-chat-app.git
cd realtime-chat-app
```

### Build the Project

```bash
mvn clean install
```

### Run the Application

```bash
mvn spring-boot:run
```

Or run the main class:

```java
ChatApplication.java
```

### Access the Application

Open your browser and navigate to:

```text
http://localhost:8080
```

Open the same URL in multiple browser tabs or windows to simulate multiple users chatting together.

## WebSocket Endpoints

### Connection Endpoint

```text
/chat
```

### Publish Message

```text
/app/sendMessage
```

### Subscribe to Messages

```text
/topic/messages
```

## Sample Message Format

```json
{
  "sender": "John",
  "content": "Hello everyone!"
}
```

## Future Enhancements

* Private messaging
* User join/leave notifications
* Online user list
* Chat rooms
* Message timestamps
* Message persistence using a database
* Authentication and authorization
* Emoji support
* File sharing

## Screenshots

Add screenshots of your application here.

```text
docs/images/chat-ui.png
```

## Learning Objectives

This project demonstrates:

* WebSocket communication in Spring Boot
* STOMP messaging protocol
* SockJS integration
* Real-time frontend updates using JavaScript
* Thymeleaf template rendering
* Responsive UI development with Bootstrap

## License

This project is licensed under the MIT License.

## Author

Developed as a learning project to understand real-time communication using Spring Boot WebSockets, SockJS, and STOMP.js.
