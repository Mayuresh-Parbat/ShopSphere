# 🛒 ShopSphere Backend

**A robust, secure, and production-ready E-Commerce Backend built with Java and Spring Boot**



## 📖 Overview

**ShopSphere Backend** is a scalable e-commerce backend application developed using the Spring Boot ecosystem. It provides secure RESTful APIs for user authentication, product management, shopping cart operations, and transactional order processing.

The application follows industry-standard software architecture practices, ensuring maintainability, scalability, and security.

---

## ✨ Features

### 🔐 Authentication & Authorization

* JWT-based authentication
* Role-based access control (Admin & Customer)
* Secure password encryption using BCrypt
* Stateless session management with Spring Security

### 📦 Product Management

* Create, Read, Update, Delete (CRUD) operations
* Product search functionality
* Category-based filtering
* Automatic inventory management
* Stock availability validation

### 🛒 Shopping Cart

* Add products to cart
* Update item quantities
* Remove cart items
* Dynamic price calculations
* User-specific cart sessions

### 📋 Order Management

* Secure checkout process
* Order history tracking
* Transactional order processing
* Automatic inventory updates
* ACID-compliant database transactions

### 🗄️ Database Management

* Spring Data JPA ORM
* Entity relationship mapping
* Database integrity constraints
* Support for MySQL and PostgreSQL

---

## 🏗️ Technology Stack

| Category   | Technology            |
| ---------- | --------------------- |
| Language   | Java 17+              |
| Framework  | Spring Boot 3.x       |
| Security   | Spring Security + JWT |
| ORM        | Spring Data JPA       |
| Database   | MySQL / PostgreSQL    |
| Build Tool | Maven                 |
| Validation | Jakarta Validation    |
| API Style  | RESTful APIs          |

---

## 📁 Project Structure

```text
src/main/java/com/shopsphere/backend/
│
├── config/          # Security, JWT and application configurations
├── controllers/     # REST API endpoints
├── dto/             # Request and response DTOs
├── models/          # JPA entities
├── repositories/    # Database repositories
├── services/        # Business logic layer
├── exceptions/      # Custom exception handling
├── security/        # JWT filters and utilities
└── ShopSphereApplication.java
```

---

## 🔄 Application Architecture

```text
Client
   │
   ▼
REST Controllers
   │
   ▼
Service Layer
   │
   ▼
Repository Layer
   │
   ▼
Database
```

The application follows a layered architecture to maintain separation of concerns and improve maintainability.

---

# 🚀 API Endpoints

## 🔑 Authentication

| Method | Endpoint             | Access |
| ------ | -------------------- | ------ |
| POST   | `/api/auth/register` | Public |
| POST   | `/api/auth/login`    | Public |

---

## 📦 Products

| Method | Endpoint                   | Access |
| ------ | -------------------------- | ------ |
| GET    | `/api/products`            | Public |
| GET    | `/api/products/{id}`       | Public |
| POST   | `/api/admin/products`      | Admin  |
| PUT    | `/api/admin/products/{id}` | Admin  |
| DELETE | `/api/admin/products/{id}` | Admin  |

---

## 🛒 Shopping Cart

| Method | Endpoint                       | Access   |
| ------ | ------------------------------ | -------- |
| GET    | `/api/cart`                    | Customer |
| POST   | `/api/cart/add`                | Customer |
| DELETE | `/api/cart/remove/{productId}` | Customer |

---

## 📋 Orders

| Method | Endpoint              | Access   |
| ------ | --------------------- | -------- |
| POST   | `/api/orders`         | Customer |
| GET    | `/api/orders/history` | Customer |

---

# ⚙️ Installation & Setup

## 1️⃣ Clone the Repository

```bash
git clone https://github.com/yourusername/shopsphere-backend.git

cd shopsphere-backend
```

---

## 2️⃣ Configure Database

Create a database:

```sql
CREATE DATABASE shopsphere;
```

---

## 3️⃣ Configure Application Properties

Update the file:

```text
src/main/resources/application.properties
```

```properties
# Database Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/shopsphere?useSSL=false&serverTimezone=UTC
spring.datasource.username=your_username
spring.datasource.password=your_password

# JPA Configuration
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect

# JWT Configuration
shopsphere.jwt.secret=YourSuperSecretKeyThatIsAtLeast256BitsLongForSecurityPurposes
shopsphere.jwt.expiration-ms=86400000
```

---

## 4️⃣ Build the Project

```bash
mvn clean install
```

---

## 5️⃣ Run the Application

```bash
mvn spring-boot:run
```

Application will start at:

```text
http://localhost:8080
```

---

# 🔐 Authentication Flow

### Register User

```http
POST /api/auth/register
```

---

### Login User

```http
POST /api/auth/login
```

```json
{
  "email": "john@example.com",
  "password": "password123"
}
```

Response:

```json
{
  "token": "jwt_token_here"
}
```

---

### Access Protected APIs

Include the JWT token in the request header:

```http
Authorization: Bearer your_jwt_token
```

---

# 🧪 API Testing

You can test the APIs using:

* Postman
* Insomnia
* cURL
* Swagger UI (if integrated)


---

# 🔒 Security Features

* JWT Authentication
* BCrypt Password Hashing
* Role-Based Authorization
* Stateless Sessions
* Input Validation
* Transaction Management
* Exception Handling
* Database Integrity Constraints

---

# 📈 Future Enhancements

* Payment Gateway Integration
* Email Verification
* Password Reset
* Product Reviews & Ratings
* Wishlist Feature
* Order Tracking
* Redis Caching
* Docker Deployment
* Microservices Architecture
* API Documentation with Swagger

---

# 🤝 Contributing

Contributions are welcome.

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push your branch
5. Open a Pull Request

---
Author 
**Mayuresh Parbat**

**Built with Java, Spring Boot, and ❤️**


