# Demo Project: Employee CRUD API

This is a simple _Node.js_ and _Express.js_ API designed to manage employee records, using _MySQL_ as the database. It implements basic _CRUD_ (Create, Read, Update, Delete) operations to facilitate employee management.

## Features

- _Add a new employee_ [api/employees] [POST]: Create a new employee record in the database.
- _Get all employees_ [api/employees] [GET]: Retrieve a list of all employees.
- _Get a single employee by ID_ [api/employees/<id>] [GET]: Fetch details of an individual employee using their unique ID.
- _Update an existing employee_ [api/employees/<id>] [PUT]: Modify the details of an existing employee.
- _Delete an employee_ [api/employees/<id>] [DELETE]: Remove an employee from the database.

## Getting Started

To run the API locally:

1. _Clone the repository_:  
   sh

   > git clone https://github.com/SoumaySoni/demo-crud-project

2. _Install dependencies_:  
   sh

   > cd demo-crud-project  
   > npm install

3. _Set up environment variables_:  
   #Copy the sample.env as .env file at the root of the project and define your database credentials:

   #copy the sample env in your root:  
   sh

   > cp sample.env .env

   #env variables

   > DB_HOST=localhost  
   > DB_USER=root  
   > DB_PASSWORD=yourpassword  
   > DB_NAME=yourdbname

4. _Start the server_:  
   sh
   > npm start

The API will be available at http://localhost:5000.

## Challenges I Encountered During Development

### 1. _Database Connection Issues_

- _Error_: Access denied for user 'root'@'localhost'
- _Solution_: I had to verify my MySQL user credentials and ensure the correct privileges were assigned to the root user.

### 2. _CORS Issues_

- _Error_: Blocked by CORS policy
- _Solution_: Configuring proper CORS settings in Express to allow cross-origin requests from the front-end.

### 3. _Environment Variables Not Loading_

- _Issue_: .env values were not being loaded into the application
- _Solution_: Ensured that dotenv was correctly configured to load environment variables and added the necessary .env file to store sensitive credentials like the database password.

### 4. **Incorrect Use of db.query**

- _Error_: TypeError: db.query is not a function
- _Solution_: I had to verify the MySQL connection setup and ensure that the query method was correctly implemented in the database configuration.

## Future Improvements

- _Authentication and Authorization_: Add user authentication to protect CRUD operations.
- _Input Validation_: Implement validation for employee data to ensure consistency.
- _Error Handling_: Improve error messages for better debugging and user feedback.
