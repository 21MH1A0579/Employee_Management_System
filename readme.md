# Employee Management System

## Overview
The **Employee Management System** is a Spring Boot web application that allows registered users to manage employees by performing CRUD operations. The application includes user authentication, employee management, and pagination.

## Technologies & Dependencies Used
The project utilizes the following dependencies:

```xml
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-data-jpa</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-security</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-thymeleaf</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>
    <dependency>
        <groupId>org.thymeleaf.extras</groupId>
        <artifactId>thymeleaf-extras-springsecurity6</artifactId>
    </dependency>
    <dependency>
        <groupId>com.mysql</groupId>
        <artifactId>mysql-connector-j</artifactId>
        <scope>runtime</scope>
    </dependency>
</dependencies>
```

## Folder Structure
```
src/main/java/com/example/demo/
│-- Controllers
│   ├── EmployeeController.java
│   ├── UserRegistrationController.java
│-- Configurations
│-- DTOs
│   ├── UserRegistrationDto.java
│-- Models
│   ├── Employee.java
│   ├── User.java
│   ├── Role.java
│-- Repositories
│   ├── EmployeeRepository.java
│   ├── UserRepository.java
│-- Services
│   ├── EmployeeService.java
│   ├── UserService.java
│-- Application.java
│
src/main/resources/
│-- static/
│   ├── css/
│-- templates/
│   ├── index.html
│   ├── registration.html
│   ├── new_employee.html
│   ├── update_employee.html
```

## Database Schema
- **employees**: Stores employee data with fields `id`, `firstName`, `lastName`, `email`.
- **user**: Stores user registration details including `id`, `firstName`, `lastName`, `email`, `password`.
- **role**: Stores user roles.
- **users_roles**: Many-to-many relationship between users and roles.

## Features
- User Registration & Authentication
- Create, Read, Update, Delete (CRUD) Employees
- Pagination (5 employees per page)
- Spring Security Integration

## API Endpoints
### Employee Management
| Method | Endpoint | Description |
|--------|---------|-------------|
| GET | `/employee/home` | View homepage with paginated employees |
| GET | `/employee/showNewEmployeeForm` | Show form to add an employee |
| POST | `/employee/saveEmployee` | Save new employee to DB |
| GET | `/employee/showFormForUpdate/{id}` | Show update employee form |
| GET | `/employee/deleteEmployee/{id}` | Delete employee by ID |
| GET | `/employee/page/{pageNo}` | Paginated employee list |

### User Registration
| Method | Endpoint | Description |
|--------|---------|-------------|
| GET | `/registration` | Show registration form |
| POST | `/registration` | Register new user |

## Setup Instructions
1. Clone the repository:
   ```sh
   git clone https://github.com/your-repo/employee-management.git
   cd employee-management
   ```
2. Configure `application.properties`:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/employee_db
   spring.datasource.username=root
   spring.datasource.password=yourpassword
   spring.jpa.hibernate.ddl-auto=update
   ```
3. Build and run the project:
   ```sh
   mvn spring-boot:run
   ```
4. Open in browser:
   ```
   http://localhost:8080
   ```

## Contributors
- CH.BRAHMENDRA(https://github.com/21MH1A0579)

