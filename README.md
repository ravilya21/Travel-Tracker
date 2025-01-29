# Travel-Tracker

🌍 Travel Tracker
Travel Tracker is a simple web application that allows users to keep track of the countries they have visited.

📌 Prerequisites
Before running this project, make sure you have the following installed:

PostgreSQL
Node.js and npm
🛠️ Setup
1️⃣ Create a PostgreSQL Database
Open pgAdmin or connect to PostgreSQL via the terminal.
Create a new database named world.
2️⃣ Create Tables
Run the following SQL commands to create the required tables:

countries Table
This table will store all available countries.
CREATE TABLE countries (
    id SERIAL PRIMARY KEY,
    country_code VARCHAR(2) ,
    country_name VARCHAR(100) NOT NULL
);

visited_countries Table
This table will store the countries that users have visited.

CREATE TABLE visited_countries (
    id SERIAL PRIMARY KEY,
    country_code VARCHAR(2) NOT NULL
);

3️⃣ Import Data into countries Table
Open pgAdmin or your PostgreSQL command-line tool.
Run the following command to import data from countries.csv into the countries table:

COPY countries (country_code, country_name)
FROM 'path/to/countries.csv'
DELIMITER ','
CSV HEADER;
    
    Replace 'path/to/countries.csv' with the actual path to your file.

4️⃣ Update Database Credentials
In the index.js file, update the database connection details:

const db = new pg.Client({
   user: "your_postgres_username",
   host: "localhost",
   database: "world",
   password: "your_postgres_password",
   port: 5432,
});

5️⃣ Install Dependencies
Run the following command to install the required dependencies:

npm install

6️⃣ Start the Server
Run the application with:

node index.js

The server should now be running at http://localhost:3000.


    

