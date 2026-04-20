# mpj.multi-messenger_backenD

# Overview
Multi Messenger Backend is a Spring Boot application that provides a centralized backend for sending messages across multiple communication platforms. The project currently supports Telegram and Discord integrations, while Slack and WhatsApp are included as future extensions.

The system receives a user request, identifies the selected platform, fetches the mapped platform account from the database, and forwards the message to the corresponding messaging service.


# Features
- Centralized backend for multi-platform messaging
- REST API for authentication and message sending
- Telegram message delivery using Telegram Bot API
- Discord message delivery using JDA
- MySQL-based storage for user-platform mappings
- Modular architecture using controller, service, repository, and model layers
- Scalable structure for adding new messaging platforms


# Technologies Used
- Java 17
- Spring Boot
- Spring Web MVC
- Spring Data JPA
- MySQL
- H2 Database
- JDA (Java Discord API)
- Maven


# Project Structure
```text
src/main/java/com/project/multimessenger
│
├── controller
│   ├── AuthController.java
│   └── MessageController.java
│
├── dto
│   ├── LoginRequest.java
│   └── MessageRequest.java
│
├── model
│   ├── Platform.java
│   ├── User.java
│   └── UserPlatformAccount.java
│
├── repository
│   ├── PlatformRepository.java
│   ├── UserRepository.java
│   └── UserPlatformAccountRepository.java
│
├── service
│   ├── DiscordService.java
│   ├── MessageService.java
│   └── UserService.java
│
└── MultimessengerApplication.java


How the Project Works
A client sends a request to the backend.
The backend checks the requested platform.
It looks up the platform in the platforms table.
It finds the user’s mapped platform account in the user_platform_accounts table.
Based on the platform:
Sends the message using Telegram Bot API
Sends the message using Discord JDA
Returns a success or failure response to the client.  
