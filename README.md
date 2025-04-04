# Demo Project: Employee CRUD API

This is a simple **Node.js** and **Express.js** API designed to manage employee records, using **MySQL** as the database. It implements basic **CRUD** (Create, Read, Update, Delete) operations to facilitate employee management.

## Features

- **Add a new employee** [api/employees] [POST]: Create a new employee record in the database.
- **Get all employees** [api/employees] [GET]: Retrieve a list of all employees.
- **Get a single employee by ID** [api/employees/<id>] [GET]: Fetch details of an individual employee using their unique ID.
- **Update an existing employee** [api/employees/<id>] [PUT]: Modify the details of an existing employee.
- **Delete an employee** [api/employees/<id>] [DELETE]: Remove an employee from the database.

## Getting Started

To run the API locally:

1. Clone the repository:

   ```sh
   > git clone https://github.com/SoumaySoni/demo-crud-project
   ```

2. Install dependencies:

   ```sh
   > cd demo-crud-project
   > npm install
   ```

3. Set Up the MySQL Database  
   #First, create a database and table in MySQL.

   ```sql
   CREATE DATABASE employee_db;

   USE employee_db;

   CREATE TABLE employees (
      id INT AUTO_INCREMENT PRIMARY KEY,
      name VARCHAR(100) NOT NULL,
      email VARCHAR(100) NOT NULL UNIQUE,
      position VARCHAR(100) NOT NULL,
      salary DECIMAL(10,2) NOT NULL
   );
   ```

4. Set up environment variables :  
   Copy the `sample.env` as `.env` file at the root of the project and define your database credentials:

   ```sh
   #copy the sample env in your root:
   > cp sample.env .env

   #env variables
   > DB_HOST=localhost
   > DB_USER=root
   > DB_PASSWORD=yourpassword
   > DB_NAME=yourdbname
   ```

5. Start the server:
   ```sh
   > npm start
   ```

The API will be available at http://localhost:5000.

## Challenges I Encountered During Development

### 1. Database Connection Issues

- Error: Access denied for user `root@localhost`
- Solution: I had to verify my MySQL user credentials and ensure the correct privileges were assigned to the root user.

### 2. CORS Issues

- Error: Blocked by `CORS` policy
- Solution: Configuring proper `CORS` settings in Express to allow cross-origin requests from the front-end.

### 3. Environment Variables Not Loading

- Issue: `.env` values were not being loaded into the application
- Solution: Ensured that dotenv was correctly configured to load environment variables and added the necessary `.env` file to store sensitive credentials like the database password.

### 4. **Incorrect Use of db.query**

- Error: TypeError: `db.query` is not a function
- Solution: I had to verify the MySQL connection setup and ensure that the query method was correctly implemented in the database configuration.
