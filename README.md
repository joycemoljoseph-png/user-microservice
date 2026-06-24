# User Microservice

A simple Spring Boot microservice for managing users. This project demonstrates the fundamentals of building microservices with Spring Boot.

## 📋 Features

- **CRUD Operations**: Create, Read, Update, and Delete users
- **REST API**: RESTful endpoints for user management
- **H2 Database**: In-memory database for easy testing and learning
- **Spring Data JPA**: Simplified data access layer
- **Docker Support**: Ready to containerize and deploy
- **Lombok**: Reduces boilerplate code

## 🏗️ Project Structure

```
src/main/java/com/example/
├── UserMicroserviceApplication.java    # Main entry point
├── controller/
│   └── UserController.java             # REST endpoints
├── service/
│   └── UserService.java                # Business logic
├── model/
│   └── User.java                       # Entity model
└── repository/
    └── UserRepository.java             # Data access
```

## 🚀 Getting Started

### Prerequisites

- Java 17 or higher
- Maven 3.6+
- Docker (optional)

### Running Locally

1. **Clone the repository**
   ```bash
   git clone https://github.com/joycemoljoseph-png/user-microservice.git
   cd user-microservice
   ```

2. **Build the project**
   ```bash
   mvn clean install
   ```

3. **Run the application**
   ```bash
   mvn spring-boot:run
   ```

The application will start on `http://localhost:8080/api`

### Running with Docker

1. **Build the Docker image**
   ```bash
   docker build -t user-microservice:1.0.0 .
   ```

2. **Run the container**
   ```bash
   docker run -p 8080:8080 user-microservice:1.0.0
   ```

Or use Docker Compose:
```bash
docker-compose up
```

## 📡 API Endpoints

### Base URL: `http://localhost:8080/api/users`

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/users` | Get all users |
| GET | `/users/{id}` | Get user by ID |
| GET | `/users/search/email?email=user@example.com` | Get user by email |
| POST | `/users` | Create a new user |
| PUT | `/users/{id}` | Update a user |
| DELETE | `/users/{id}` | Delete a user |

### Request Body (POST/PUT)
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "phone": "1234567890",
  "address": "123 Main St, City"
}
```

### Response Example
```json
{
  "id": 1,
  "name": "John Doe",
  "email": "john@example.com",
  "phone": "1234567890",
  "address": "123 Main St, City"
}
```

## 🗄️ Database

The application uses **H2 in-memory database** for simplicity during development.

### H2 Console
- URL: `http://localhost:8080/api/h2-console`
- JDBC URL: `jdbc:h2:mem:testdb`
- Username: `sa`
- Password: (leave empty)

## 📚 Technology Stack

- **Spring Boot**: 3.1.5
- **Spring Data JPA**: ORM and database access
- **H2 Database**: In-memory relational database
- **Lombok**: Boilerplate reduction
- **Maven**: Build and dependency management

## 🧪 Testing

Run tests with:
```bash
mvn test
```

## 📝 Key Concepts Covered

1. **Spring Boot Application**: Understanding the main entry point
2. **REST Controller**: Creating HTTP endpoints
3. **Service Layer**: Implementing business logic
4. **Repository Pattern**: Data access abstraction
5. **Entity Models**: JPA entity mapping
6. **Dependency Injection**: Spring's IoC container
7. **Database Configuration**: H2 setup and configuration
8. **Docker**: Containerizing the application

## 🔧 Configuration

All configuration is in `src/main/resources/application.yml`:

```yaml
spring:
  jpa:
    hibernate:
      ddl-auto: create-drop  # Auto-create tables on startup
  datasource:
    url: jdbc:h2:mem:testdb
```

## 📖 Learning Resources

- [Spring Boot Documentation](https://spring.io/projects/spring-boot)
- [Spring Data JPA](https://spring.io/projects/spring-data-jpa)
- [Building REST Services with Spring](https://spring.io/guides/gs/rest-service/)

## 🤝 Contributing

Feel free to fork this project and submit pull requests for improvements.

## 📄 License

This project is open source and available under the MIT License.

---

**Happy Learning!** 🎉

For questions or issues, please open a GitHub issue in this repository.
