# E-Commerce Web Application

A Java-based e-commerce web application built using **Spring Boot, JSP, Hibernate, Spring Security, and MySQL**. The application follows a layered MVC architecture and provides separate workflows for administrators and customers, with role-based authentication and authorization.

**Repository:** [SenseiRonnie / E-commerce](https://github.com/SenseiRonnie/E-commerce)

---

## Features

- Server-rendered web application using JSP and JSTL.
- Secure authentication and role-based authorization using Spring Security.
- Admin dashboard for managing products, categories, and customers.
- Customer registration, login, and profile management.
- Product browsing and database-driven persistence.
- Layered architecture with Controller, Service, and DAO components.
- Hibernate ORM integration using a custom `SessionFactory`.
- MySQL database integration.
- Jenkins pipeline configuration for CI/CD setup.

## Technology Stack

| Technology | Purpose |
|---|---|
| Java 11 | Backend programming |
| Spring Boot 2.6.4 | Application framework |
| Spring MVC | Web architecture |
| Spring Security | Authentication and authorization |
| Hibernate ORM | Object-relational mapping |
| JSP & JSTL | Server-side rendering |
| MySQL 8 | Relational database |
| Maven | Dependency and build management |
| Jenkins | CI/CD pipeline |

## Project Architecture

The application follows a layered MVC architecture.

```text
E-commerce/
│
├── src/
│   └── main/
│       ├── java/
│       │   └── com/jtspringproject/JtSpringProject/
│       │       ├── configuration/
│       │       ├── controller/
│       │       ├── dao/
│       │       ├── models/
│       │       ├── services/
│       │       ├── repository/
│       │       ├── HibernateConfiguration.java
│       │       └── JtSpringProjectApplication.java
│       │
│       ├── resources/
│       │   └── application.properties
│       │
│       └── webapp/
│           └── views/
│               └── *.jsp
│
├── basedata.sql
├── pom.xml
└── README.md
```

## Getting Started

### Prerequisites

Make sure the following software is installed:

- Java 11 or later
- Maven 3.8+
- MySQL 8 or MariaDB
- Git

### 1. Clone the repository

```bash
git clone https://github.com/SenseiRonnie/E-commerce.git
```

Navigate to the project directory:

```bash
cd E-commerce
```

### 2. Configure the database

Create a MySQL database or allow the application to create it automatically.

Update the following configuration in:

`src/main/resources/application.properties`

```properties
db.driver=com.mysql.cj.jdbc.Driver
db.url=jdbc:mysql://localhost:3306/ecommjava?createDatabaseIfNotExist=true
db.username=your_db_user
db.password=your_db_password

hibernate.dialect=org.hibernate.dialect.MySQL5Dialect
hibernate.show_sql=true
hibernate.hbm2ddl.auto=update
entitymanager.packagesToScan=com
```

Replace the database username and password with your local MySQL credentials.

**Security note:** Never commit actual database passwords, API keys, or other sensitive credentials to GitHub.

### 3. Initialize sample data (Optional)

The repository includes `basedata.sql` for initializing sample categories, users, and products.

Execute the SQL script against your MySQL database if sample data is required.

Note: Any sample credentials included in the SQL script should only be used in a development environment.

### 4. Build and run the application

Build the project:

```bash
mvn clean package
```

Start the Spring Boot application:

```bash
mvn spring-boot:run
```

Once the application starts, open:

**http://localhost:8080/**

## Application Modules

### Customer Module

- Customer registration
- User authentication and login
- Product browsing
- Profile management

### Administrator Module

- Admin authentication
- Admin dashboard
- Product management
- Category management
- Customer listing

## Application Endpoints

### Public and Customer Routes

| Endpoint | Description |
|---|---|
| `/` | Application home page |
| `/login` | Customer login |
| `/register` | Customer registration |
| `/newuserregister` | User registration processing |
| `/user/products` | Product listing |
| `/profileDisplay` | Customer profile |

### Administrator Routes

| Endpoint | Description |
|---|---|
| `/admin/` | Admin home |
| `/admin/Dashboard` | Admin dashboard |
| `/admin/products` | Product management |
| `/admin/categories` | Category management |
| `/admin/customers` | Customer listing |

## Security

Spring Security is used to protect application resources.

- Administrator routes under `/admin/**` require the `ADMIN` role.
- Customer routes require the `USER` role.
- Separate login pages are provided for administrators and customers.
- CSRF protection is enabled for form submissions.

## Build and Testing

Run the following command to build and verify the project:

```bash
mvn clean verify
```

**Database requirement:** Tests that initialize the Spring application context may require a running MySQL instance with valid database credentials.

## CI/CD

A Jenkins pipeline configuration is included as a starting point for CI/CD automation.

The pipeline includes the following stages:

1. Checkout
2. Build
3. Test
4. Deploy (placeholder)

The deployment stage requires environment-specific configuration, credentials, and deployment instructions.

## Troubleshooting

**1. Could not resolve placeholder `db.driver`**

- Verify that all required `db.*` properties are configured in `application.properties`.

**2. JSP pages are not rendering**

- Verify the JSP view configuration.
- Check that `spring.mvc.view.prefix=/views/` is configured.
- In IntelliJ IDEA, check the run configuration working directory.

**3. Application fails during database initialization**

- Ensure MySQL is running.
- Verify database credentials.
- Confirm that the configured database is accessible.

## Future Improvements

Potential improvements for the application include:

- Shopping cart functionality
- Order management and checkout
- Product search and filtering
- Payment gateway integration
- REST API development
- Docker-based deployment
- Improved automated test coverage
- Application monitoring and logging
- Performance optimization and caching

## Author

**Ronnie (SenseiRonnie)**

GitHub: [@SenseiRonnie](https://github.com/SenseiRonnie)

Repository: [E-commerce](https://github.com/SenseiRonnie/E-commerce)

---

*Maintained by SenseiRonnie.*

*This repository contains an adapted e-commerce project. Refer to the original project's license and attribution requirements where applicable.*