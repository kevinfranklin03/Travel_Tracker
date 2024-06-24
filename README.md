Certainly! Here's the README.md file converted into a proper format:

---

# Visited Countries Tracker

This is a simple web application built with Node.js, Express, and PostgreSQL to track the countries you've visited. Users can add countries and view a list of visited countries with the total count.

## Features

- Add countries to your visited list.
- View a list of visited countries with the total count.
- Handles errors gracefully, such as adding a non-existent country or a duplicate entry.

## Prerequisites

Make sure you have the following installed on your local machine:

- [Node.js and npm](https://nodejs.org/en/download/package-manager)
- [PostgreSQL](https://www.postgresql.org/download/)

## Getting Started

Follow these steps to set up and run the project locally:

### Installation

Clone the repository:

```bash
git clone https://github.com/your-username/visited-countries-tracker.git
cd visited-countries-tracker
```

Install dependencies:

```bash
npm install
```

### Database Setup

1. Make sure PostgreSQL is installed and running.

2. Create a new database named `world`:

   ```sql
   CREATE DATABASE world;
   ```

3. Connect to the `world` database and create necessary tables:

   ```sql
   \c world

   CREATE TABLE countries (
       country_code CHAR(3) PRIMARY KEY,
       country_name VARCHAR(100) NOT NULL
   );

   CREATE TABLE visited_countries (
       country_code CHAR(3) REFERENCES countries(country_code) ON DELETE CASCADE
   );
   ```

4. Populate the `countries` table with country codes and names.

5. Configure the database connection in `index.js` with your PostgreSQL credentials:

   ```javascript
   const db = new pg.Client({
       user: "postgres",
       host: "localhost",
       database: "world",
       password: "your_password",
       port: 5432,
   });
   ```

### Running the Application

Start the application:

```bash
npm start
```

The server will start on `http://localhost:3000`.

### Usage

1. Open `http://localhost:3000` in your browser.
2. Enter the name of the country you've visited in the input field and submit.
3. The application will display the updated list of visited countries and the total count.

### Error Handling

- If you try to add a country that doesn't exist in the database, an error message will be displayed.
- If you try to add a country that's already on your visited list, an error message will be displayed.

## Dependencies

- [Express](https://expressjs.com/)
- [Body-Parser](https://www.npmjs.com/package/body-parser)
- [PG](https://www.npmjs.com/package/pg)
- [EJS](https://www.npmjs.com/package/ejs)

## Contributing

We welcome contributions! Feel free to fork the project, create a feature branch, and submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

## Contact

For any questions or comments, please open an issue on [GitHub](https://github.com/your-username/visited-countries-tracker).

---

This README provides clear instructions on how to set up, run, and use the application, along with important details about dependencies, error handling, contributing guidelines, and licensing information.
