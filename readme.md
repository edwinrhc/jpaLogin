# Spring Boot Security + Spring Security + User Details Service

This project demonstrates the integration of **Spring Boot Security** with **Spring Security** and a custom **UserDetailsService** implementation for authentication and authorization.

## Features
- **Spring Boot 3.0**
- **Spring Security** for secure authentication and authorization.
- Custom **UserDetailsService** implementation to manage user details.
- In-memory or database-backed user storage for authentication.
- Role-based access control (ADMIN, USER roles).

## Requirements
- **Java 17** or higher.
- **Maven 3.8+**
- **Spring Boot 3.0+**
- **MySQL** (Optional for persistent user storage).

## Getting Started

### Clone the Repository
```bash
git clone https://github.com/<your-username>/spring-security-example.git
cd spring-security-example
```

### Configure the Application
1. Update the `application.yml` or `application.properties` file:
    - Set database connection details (if using MySQL).
    - Configure the port and other application properties.

Example `application.yml`:
```yaml
server:
  port: 8080

spring:
  datasource:
    url: jdbc:mysql://localhost:3306/spring_security
    username: root
    password: password
    driver-class-name: com.mysql.cj.jdbc.Driver
  jpa:
    hibernate:
      ddl-auto: update
  security:
    user:
      name: admin
      password: admin
```

2. Ensure you have a running MySQL instance and create a database `spring_security` if needed:
```sql
CREATE DATABASE spring_security;
```

### Build and Run the Application
```bash
mvn clean install
mvn spring-boot:run
```

### Access the Application
- Default URL: `http://localhost:8080`
- Login credentials:
    - Username: `admin`
    - Password: `admin`

## Endpoints
| HTTP Method | Endpoint       | Description                       | Role Required |
|-------------|----------------|-----------------------------------|---------------|
| GET         | `/api/home`    | Public endpoint                  | None          |
| GET         | `/api/admin`   | Admin-only endpoint              | ADMIN         |
| GET         | `/api/user`    | User-specific endpoint           | USER          |

## Technologies Used
- **Spring Boot**: For building the application.
- **Spring Security**: For authentication and authorization.
- **H2/MySQL**: Database for user storage.
- **Thymeleaf** (Optional): For rendering views (if applicable).

## Additional Notes
- The project can be extended to include JWT-based authentication.
- Users can be fetched from an external database or managed through in-memory storage.

## References
- [Spring Boot Documentation](https://spring.io/projects/spring-boot)
- [Spring Security Documentation](https://spring.io/projects/spring-security)


---
Feel free to fork, modify, and contribute to this project!

