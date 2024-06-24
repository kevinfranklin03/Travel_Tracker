# Visited Countries Tracker

A simple web application built with Node.js, Express, and PostgreSQL to track countries you've visited. Users can add countries they've visited, and the application will display a list of these countries along with the total number of visited countries.

## Features

- Add a country to the visited list.
- Display the list of visited countries.
- Handle errors gracefully, such as adding a country that does not exist or has already been added.

## Prerequisites

- Node.js and npm
- PostgreSQL

## Getting Started

Follow these instructions to set up and run the project locally.

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/your-username/visited-countries-tracker.git
   cd visited-countries-tracker
Install dependencies

bash
Download
Copy code
npm install
Set up the database

Ensure PostgreSQL is installed and running on your machine.

Create a new database named world:

sql
Download
Copy code
CREATE DATABASE world;
Create the necessary tables:

sql
Download
Copy code
\c world

CREATE TABLE countries (
  country_code CHAR(3) PRIMARY KEY,
  country_name VARCHAR(100) NOT NULL
);

CREATE TABLE visited_countries (
  country_code CHAR(3) REFERENCES countries(country_code) ON DELETE CASCADE
);
Populate the countries table with country codes and names. You can find datasets online or manually insert data for testing.

Configure the database connection

Update the database configuration in index.js:

javascript
Download
Copy code
const db = new pg.Client({
  user: "postgres",
  host: "localhost",
  database: "world",
  password: "your_password",
  port: 5432,
});
Run the application

bash
Download
Copy code
npm start
The server will be running on http://localhost:3000.

Usage
Open http://localhost:3000 in your browser.
Add the name of the country you have visited in the input field and submit.
The list of visited countries and the total number will be displayed on the home page.
Error Handling
If you try to add a country that does not exist in the countries table, an error message will be displayed.
If you try to add a country that has already been added, an error message will be displayed.
Dependencies
Express
Body-Parser
PG
EJS
Contributing
Feel free to fork the project, create a feature branch, and submit a pull request. Contributions are welcome!

License
This project is licensed under the MIT License - see the LICENSE file for details.

Contact
For any questions or comments, please open an issue on GitHub.

