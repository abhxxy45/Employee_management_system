# Employee Management System

Desktop CRUD application for managing employee records using Java Swing and MySQL.

## Tech Stack

| Layer | Technology |
|-------|------------|
| **Language** | Java |
| **GUI** | Java Swing |
| **Database** | MySQL |
| **Connectivity** | JDBC |
| **Build** | Eclipse (no Maven/Gradle) |
| **Charting** | JFreeChart 1.5.6 |

## Project Structure

```
Employee_management_system/
├── src/                          # Java source (default package)
│   ├── *.java                    # Main application classes
├── employee.sql                  # Database schema
├── mysql-connector-java-8.0.30.jar  # MySQL JDBC driver
├── jfreechart-1.5.6.jar         # Charting library
├── .classpath                    # Eclipse classpath
├── .project                      # Eclipse project
└── README.md
```

## Features

- **Employee CRUD**: Create, read, update, delete employee records
- **Search & Filter**: Find employees by ID, name, department
- **Data Validation**: Input validation for all fields
- **MySQL Integration**: Persistent storage via JDBC
- **Charting**: JFreeChart visualizations (reports)
- **Swing GUI**: Desktop interface with forms and tables

## Database Schema

The `employee.sql` file creates:
```sql
CREATE DATABASE IF NOT EXISTS employee_db;
USE employee_db;

CREATE TABLE employees (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE,
    phone VARCHAR(20),
    department VARCHAR(50),
    designation VARCHAR(50),
    salary DECIMAL(10,2),
    join_date DATE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## Setup Instructions

### Prerequisites
- Java 8+ (JDK)
- MySQL 8.0+
- Eclipse IDE (or any Java IDE)

### Installation

```bash
# Clone repository
git clone https://github.com/abhxxy45/Employee_management_system.git
cd Employee_management_system

# Setup database
mysql -u root -p < employee.sql

# Open in Eclipse
# File → Import → Existing Projects into Workspace
# Select project root directory

# Add JARs to Build Path:
# Right-click project → Build Path → Configure Build Path
# Libraries → Add External JARs → Select mysql-connector-java-8.0.30.jar and jfreechart-1.5.6.jar

# Run Main class
```

### Database Configuration

Update database connection in the main Java class:
```java
String url = "jdbc:mysql://localhost:3306/employee_db";
String user = "root";
String password = "your_password";
```

## Building & Running

### In Eclipse
1. Import as existing project
2. Add JARs to build path
3. Run `Main.java` (or equivalent entry point)

### Command Line (if compiled)
```bash
javac -cp ".:mysql-connector-java-8.0.30.jar:jfreechart-1.5.6.jar" src/*.java
java -cp ".:mysql-connector-java-8.0.30.jar:jfreechart-1.5.6.jar" Main
```

## Screenshots

*To be added*

## License

MIT License — see [LICENSE](LICENSE) for details.

---

**Repository**: https://github.com/abhxxy45/Employee_management_system