This is a simple web application built with Node.js, Express, and PostgreSQL to track the countries you've visited. Users can add countries and view a list of visited countries with the total count.

Features
Add countries to your visited list.
View a list of visited countries with the total count.
Handles errors gracefully, such as adding a non-existent country or a duplicate entry.
Prerequisites
Node.js and npm installed (https://nodejs.org/en/download/package-manager)
PostgreSQL installed and running (https://www.postgresql.org/download/)
Getting Started
Follow these steps to set up and run the project locally:

Installation
Clone the repository:

Bash
git clone https://github.com/your-username/visited-countries-tracker.git
cd visited-countries-tracker
Use code with caution.
content_copy
Install dependencies:

Bash
npm install
Use code with caution.
content_copy
Set up the database:

Make sure PostgreSQL is installed and running.

Create a new database named world:

SQL
CREATE DATABASE world;
Use code with caution.
content_copy
Create the necessary tables:

SQL
\c world

CREATE TABLE countries (
    country_code CHAR(3) PRIMARY KEY,
    country_name VARCHAR(100) NOT NULL
);

CREATE TABLE visited_countries (
    country_code CHAR(3) REFERENCES countries(country_code) ON DELETE CASCADE
);
Use code with caution.
content_copy
Populate the countries table with country codes and names. You can find datasets online or manually insert data for testing purposes.

Configure the database connection:

Update the database configuration in index.js with your PostgreSQL credentials:

JavaScript
const db = new pg.Client({
    user: "postgres",
    host: "localhost",
    database: "world",
    password: "your_password",
    port: 5432,
});
Use code with caution.
content_copy
Run the application:

Bash
npm start
Use code with caution.
content_copy
The server will start on http://localhost:3000.

Usage
Open http://localhost:3000 in your browser.
Enter the name of the country you've visited in the input field and submit.
The application will display the updated list of visited countries and the total count.
Error Handling
If you try to add a country that doesn't exist in the database, an error message will be displayed.
If you try to add a country that's already on your visited list, an error message will be displayed.
Dependencies
Express - https://expressjs.com/
Body-Parser - https://www.npmjs.com/package/body-parser
PG - https://www.npmjs.com/package/pg
EJS - https://www.npmjs.com/package/ejs
Contributing
We welcome contributions! Feel free to fork the project, create a feature branch, and submit a pull request.

License
This project is licensed under the MIT License - see the LICENSE file for details.

Contact
For any questions or comments, please open an issue on GitHub.
