**Student Management System API**

A RESTful Web API built using ASP.NET Core for managing student records with secure authentication using JWT (JSON Web Token).

🚀 **Features**
🔐 JWT Authentication & Authorization
👨‍🎓 Manage Students (CRUD Operations)
📄 Swagger API Documentation
🧾 Clean Architecture (Controller → Service → Repository)
⚙️ Entity Framework Core (SQL Server)
🌐 Global Exception Handling
📦 DTO-based Request Handling (Secure & Clean)
🛠️** Technologies Used**
ASP.NET Core Web API
Entity Framework Core
SQL Server
JWT Authentication
Swagger (Swashbuckle)
AutoWrapper (Standard API Responses)
📁 **Project Structure**
StudentManagementSystem
│
├── Controllers
│   └── StudentsController.cs
│
├── Services
│   └── StudentService.cs
│
├── Repositories
│   └── StudentRepository.cs
│
├── Data
│   ├── DatabaseContext.cs
│   └── Entities
│
├── Models (DTOs)
│   ├── AddStudent.cs
│   └── EditStudentDto.cs
│
└── Program.cs
⚙️ Setup Instructions
1️⃣ **Clone the Repository**
git clone https://github.com/your-username/student-management-api.git
cd student-management-api
2️⃣ **Configure Database**

Update appsettings.json:

"ConnectionStrings": {
  "StudentManagementSystemDb": "Server=YOUR_SERVER;Database=StudentDb;Trusted_Connection=True;TrustServerCertificate=True;"
}
3️⃣ **Configure JWT**
"Jwt": {
  "Key": "your_secret_key_here",
  "Issuer": "your_issuer",
  "Audience": "your_audience"
}
4️⃣ **Run Migrations**
dotnet ef database update
5️⃣ **Run the Application**
dotnet run
📘 **API Documentation** (Swagger)

Once the application is running, open:

https://localhost:7220/swagger
🔐 **Authentication**
Get Token

Use your Auth endpoint (example):

POST /auth/login
Use Token in Swagger / Postman
Authorization: Bearer <your_token>
📌 API Endpoints
👨‍🎓 **Students**
Method	Endpoint	Description
GET	/Students	Get all students
POST	/Students	Add new student
PUT	/Students	Update logged-in student
DELETE	/Students/{id}	Delete student by ID
📥 Sample Requests
➕ **Add Student**
{
  "name": "Mounika",
  "email": "test@gmail.com",
  "age": 25,
  "course": "DotNet"
}
✏️ **Update Student**
{
  "name": "Mounika Updated",
  "age": 26,
  "course": "C# Advanced"
}
⚠️** Error Handling**

Global exception handling is implemented using custom middleware.

Example response:

{
  "message": "Internal Server Error",
  "statusCode": 500
}
🔒** Security**
All endpoints (except login) are protected using JWT
User identity is extracted from token claims
Email is used to identify the logged-in student
🧠 **Best Practices Used**
DTOs to avoid over-posting
Layered Architecture
Dependency Injection
Logging using ILogger
Secure API endpoints
📌** Future Enhancements**
Role-based Authorization (Admin/User)
Pagination & Filtering
File Upload (Student Documents)
Unit Testing

👩‍💻 Author
**Mounika G**
