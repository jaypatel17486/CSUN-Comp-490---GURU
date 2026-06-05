# 👥 GURU - Student Feedback Management Platform

An enterprise-level student feedback management system that enables educational institutions to collect, organize, and analyze student feedback efficiently. Built with Java, JDBC, and MySQL for robust performance and scalability.

## 📋 Overview

GURU (Gather User Responses Unified) is a comprehensive feedback platform developed for **CSUN Comp-490 (Database Design)** course. It demonstrates advanced database architecture, complex SQL queries, and object-oriented programming principles in a real-world application.

## ✨ Key Features

- **Feedback Collection**: Easy-to-use interface for students to submit feedback
- **Feedback Management**: Create, read, update, and delete feedback entries
- **Anonymous Submissions**: Option for anonymous feedback
- **Search & Filter**: Advanced filtering by course, instructor, date, and rating
- **Analytics Dashboard**: View feedback statistics and trends
- **Data Integrity**: Comprehensive data validation and constraints
- **Multi-User Support**: Support for multiple student and instructor accounts
- **Role-Based Access**: Different permissions for students, instructors, and admins

## 🛠️ Technology Stack

| Component | Technology |
|-----------|------------|
| **Backend** | Java |
| **Database** | MySQL |
| **Database Connectivity** | JDBC (Java Database Connectivity) |
| **UI** | Java Swing / Console Interface |
| **Version Control** | Git |

## 📁 Project Structure

```
CSUN-Comp-490---GURU/
├── src/
│   ├── main/
│   │   ├── Main.java              # Application entry point
│   │   ├── database/
│   │   │   ├── DatabaseConnection.java
│   │   │   └── DatabaseManager.java
│   │   ├── models/
│   │   │   ├── Student.java
│   │   │   ├── Instructor.java
│   │   │   ├── Feedback.java
│   │   │   └── Course.java
│   │   ├── services/
│   │   │   ├── FeedbackService.java
│   │   │   ├── StudentService.java
│   │   │   └── InstructorService.java
│   │   └── ui/
│   │       └── MainUI.java
│   └── test/
│       └── TestCases.java
├── database/
│   ├── schema.sql          # Database schema
│   └── sample_data.sql     # Sample data
├── pom.xml                 # Maven dependencies (if using Maven)
└── README.md
```

## 🚀 Getting Started

### Prerequisites
- Java JDK 8+
- MySQL 5.7+
- JDBC Driver for MySQL

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/jaypatel17486/CSUN-Comp-490---GURU.git
cd CSUN-Comp-490---GURU
```

2. **Setup the database**
```bash
# Create database and tables
mysql -u root -p < database/schema.sql

# (Optional) Load sample data
mysql -u root -p < database/sample_data.sql
```

3. **Configure database connection**
- Edit `src/main/database/DatabaseConnection.java`
- Update MySQL credentials:
```java
private static final String URL = "jdbc:mysql://localhost:3306/guru_db";
private static final String USER = "your_username";
private static final String PASSWORD = "your_password";
```

4. **Compile the project**
```bash
javac -d bin src/main/*.java
```

5. **Run the application**
```bash
java -cp bin:lib/mysql-connector-java-8.0.jar Main
```

## 📊 Database Schema

The system uses a well-designed MySQL database with the following core tables:

- **students**: Student account information
- **instructors**: Instructor profiles and details
- **courses**: Course information and metadata
- **feedback**: Feedback submissions and ratings
- **feedback_responses**: Detailed feedback content
- **ratings**: Rating categories and scales

### Key Database Features:
- ✅ Primary and Foreign Keys for referential integrity
- ✅ Indexes for optimized query performance
- ✅ Constraints for data validation
- ✅ Normalized schema (3NF) design

## 🔧 Core Classes & Methods

### FeedbackService
```java
public void submitFeedback(Feedback feedback)
public List<Feedback> getFeedbackByCourse(int courseId)
public List<Feedback> getFeedbackByInstructor(int instructorId)
public void updateFeedback(Feedback feedback)
public void deleteFeedback(int feedbackId)
public double calculateAverageRating(int courseId)
```

### StudentService
```java
public Student getStudentById(int studentId)
public List<Student> getAllStudents()
public void registerStudent(Student student)
public void updateStudentProfile(Student student)
```

### DatabaseConnection
```java
public static Connection getConnection()
public static void closeConnection(Connection conn)
```

## 💡 What I Learned

- ✅ Advanced database design and schema normalization
- ✅ Complex SQL queries and JOIN operations
- ✅ JDBC connection pooling and connection management
- ✅ Object-Oriented Programming with Java
- ✅ Exception handling and error management
- ✅ Data validation and integrity constraints
- ✅ Transaction management in databases
- ✅ Performance optimization with indexes

## 📈 Query Examples

### Get average rating for a course
```sql
SELECT AVG(rating) as average_rating 
FROM feedback 
WHERE course_id = ? 
GROUP BY course_id;
```

### Get top-rated instructors
```sql
SELECT instructor_id, COUNT(*) as feedback_count, AVG(rating) as avg_rating
FROM feedback
GROUP BY instructor_id
ORDER BY avg_rating DESC
LIMIT 10;
```

## 🔒 Security Features

- ✅ SQL Injection prevention using Prepared Statements
- ✅ Input validation and sanitization
- ✅ Secure password handling
- ✅ User authentication

## 🔄 Future Enhancements

- [ ] Web-based interface (Spring Boot/JSP)
- [ ] Real-time notifications
- [ ] Advanced analytics and reporting
- [ ] Export reports to PDF/Excel
- [ ] API for third-party integration
- [ ] Machine learning for feedback sentiment analysis

## 📝 Course Information

- **Course**: CSUN Comp-490 (Database Design)
- **Institution**: California State University, Northridge

## 👤 Author

**Jay Patel**
- GitHub: [@jaypatel17486](https://github.com/jaypatel17486)
- Email: jay.171124@icloud.com

## 📄 License

This project is created for educational purposes as part of CSUN coursework.

## 🤝 Contributing

This is an academic project. For suggestions or improvements, feel free to open an issue or contact me directly.

---

**Last Updated**: June 2026
