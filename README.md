# Student-Management
Project Name: Student Management API
Project Description
The Student Management API is a RESTful API designed to manage and retrieve student data. This project provides an interface to perform CRUD (Create, Read, Update, Delete) operations for student records. It supports adding, retrieving, updating, and deleting students, while validating input data for correctness. The API is built using Node.js and Express.js, and it can easily be set up and run locally for development and testing purposes.
________________________________________
Setup and Running the Project Locally
Prerequisites:
•	Node.js (version 14.x or higher)
•	npm (Node Package Manager)
Steps to Set Up:
1.	Clone the Repository:
First, clone the zip repository to your local machine:
bash
cd student-crud
2.	Install Dependencies:
Navigate to the project directory and install the required npm packages:
bash
npm install express mysql2 body-parser
npm install --save-dev nodemon
3.	Start the Server:
To run the application locally, start the server using the following command:
bash
npm start
The application will be available at http://localhost:3000.
________________________________________
API Documentation
1. GET /students
•	Description: Retrieve a list of all students, with pagination support.
•	Query Parameters:
o	page (optional, default: 1) - The page number to retrieve.
o	limit (optional, default: 10) - Number of students per page.
Request Example:
bash
GET /students?page=1&limit=10
Response:
json
Copy code
{
  "page": 1,
  "totalPages": 5,
  "totalStudents": 50,
  "students": [
    {
      "id": 1,
      "name": "Raja",
      "age": 20,
      "email": "Raja@example.com"
    },
    ...
  ]
}
________________________________________
2. GET /students/
•	Description: Retrieve detailed information for a specific student by ID.
•	Request Example:
bash
GET /students/1
Response:
json
{
  "id": 1,
  "name": "Raja",
  "age": 20,
  "email": "Raja@example.com"
}
________________________________________
3. POST /students
•	Description: Create a new student record.
•	Request Body (JSON format):
json
{
  "name": "Raja",
  "age": 22,
  "email": "Raja@example.com"
}
Response:
json
{
  "id": 2,
  "name": "Raja",
  "age": 22,
  "email": "Raja@example.com"
}
________________________________________
4. PUT /students/
•	Description: Update the details of an existing student.
•	Request Example:
bash
PUT /students/2
Request Body (JSON format):
json
{
  "name": "Raja Updated",
  "age": 23,
  "email": "Raja.updated@example.com"
}
Response:
json
{
  "id": 2,
  "name": "Raja Updated",
  "age": 23,
  "email": "Raja.updated@example.com"
}
________________________________________
5. DELETE /students/
•	Description: Delete a student record.
•	Request Example:
bash
DELETE /students/2
Response:
json
{
  "message": "Student deleted successfully."
}
________________________________________
Additional Instructions
Data Validation
The application ensures that any student data submitted is properly validated to confirm:
•	name must be a non-empty string.
•	age must be a positive integer.
•	email must be a valid email address.
Pagination Support
For the endpoint GET /students, pagination is provided to handle large datasets. The page and limit query parameters determine which set of records is returned. If no parameters are specified, the default values of page=1 and limit=10 will be used.
Error Handling
If a request is made with invalid data, the API will respond with a 400 Bad Request error and a description of the validation issue.
________________________________________
Conclusion
This API serves as a foundational backend for student management, with basic CRUD operations and pagination support. It can easily be extended with additional functionality such as authentication, advanced search, or more complex data relationships.

