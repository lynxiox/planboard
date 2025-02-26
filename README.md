# **Planboard**

## **Project Overview**

This is a task management application built with a microservices architecture, allowing users to create, update, track, and delete tasks. It also includes features for user registration, authentication, and daily email notifications at midnight, summarizing the completed tasks from the past day, the number of tasks still pending, and a welcome message.

This project was developed based on the [technical specification](https://zhukovsd.github.io/java-backend-learning-course/projects/task-tracker/).

---

## **Technologies Used**

This project utilizes the following technologies:

- **Java 17**
- **Spring Boot**
- **PostgreSQL**
- **Flyway**
- **JWT**
- **Kafka**
- **Gradle**
- **JUnit5**
- **Mockito**
- **Docker**
- **GitHub Actions**

---
## **About Services**
### [planboard-api](https://github.com/lynxiox/planboard-api)

This service exposes a REST API for managing users and tasks, securing access with JWT-based authentication. It handles user registration, authentication, and task management, including creation, updates, deletion, and viewing.

### [planboard-email-sender](https://github.com/lynxiox/planboard-email-sender)

This service sends email notifications by listening for messages from Kafka, processing the data, and using Spring Mail to send the emails.

### [planboard-scheduler](https://github.com/lynxiox/planboard-scheduler)

This service schedules daily tasks, generates 24-hour task reports for all users, and sends them to a Kafka queue for processing by the email sender service.

### [planboard-frontend](https://github.com/lynxiox/planboard-frontend)

This service is a frontend application that interacts with planboard-api for task management and user operations.

## **Running Locally**

1. **Clone the repository:**
   ```bash
   git clone https://github.com/lynxiox/planboard.git
   cd planboard
   ```

2. **Set up environment variables:**
   Open the `.env` file and fill in the required variables (e.g., database credentials, API keys, etc.) with your own values.

3. **Start the application using Docker Compose:**
   ```bash
   docker-compose up --build
   ```
---

## **API Documentation**

You can test the API using Swagger:
`http://localhost:8080/swagger-ui/index.html`