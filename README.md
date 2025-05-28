# Article Management CRUD API

## Overview

This project implements a simple **CRUD (Create, Read, Update, Delete)** RESTful API for managing articles using **Node.js**, **Express**, and **MySQL**.

The API provides endpoints to add new articles, retrieve articles by ID or all articles, update an article’s rating or status, and delete articles. This backend service can be used as a foundation for article or blog management systems.


## Features

- Add new articles (`POST /articles`)
- Retrieve article by ID (`GET /articles/:id`)
- Retrieve all articles (`GET /articles`)
- Update article rating and status (`PUT /articles/:id`)
- Delete an article (`DELETE /articles/:id`)

---

## Technology Stack

- **Node.js**: JavaScript runtime environment
- **Express**: Web framework for Node.js
- **MySQL**: Relational database management system
- **dotenv**: Manage environment variables securely
- **cors**: Enable Cross-Origin Resource Sharing

---

## Getting Started

### Prerequisites

- Node.js installed ([https://nodejs.org/](https://nodejs.org/))
- MySQL server installed ([https://dev.mysql.com/downloads/mysql/](https://dev.mysql.com/downloads/mysql/))
- MySQL Workbench (optional, for database management)

### Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/YourUsername/article-crud-api.git
   cd article-crud-api
````

2. Install dependencies:

   ```bash
   npm install
   ```

3. Setup your database:

   * Open MySQL Workbench or command line
   * Run the SQL script in `create_table.sql` to create the database and articles table

4. Configure environment variables:

   * Create a `.env` file in the project root
   * Add your database credentials and server port:

     ```
     DB_HOST=localhost
     DB_USER=root
     DB_PASSWORD=yourpassword
     DB_NAME=articleDB
     PORT=3000
     ```

### Running the Server

Start the Node.js server:

```bash
node server.js
```

The API will be running on `http://localhost:3000`

---

## API Endpoints

| Method | Endpoint        | Description                      | Request Body (JSON)                                                           |
| ------ | --------------- | -------------------------------- | ----------------------------------------------------------------------------- |
| POST   | `/articles`     | Add a new article                | `{ "title": "", "description": "", "author": "", "status": "", "rating": 0 }` |
| GET    | `/articles/:id` | Get article by ID                | N/A                                                                           |
| GET    | `/articles`     | Get all articles                 | N/A                                                                           |
| PUT    | `/articles/:id` | Update article rating and status | `{ "rating": 0, "status": "" }`                                               |
| DELETE | `/articles/:id` | Delete an article                | N/A                                                                           |

---

## Testing

You can test the API endpoints using tools like **Postman** or **Swagger**.

Sample requests and responses are included in the `/docs` folder (if you create documentation).

---

## Project Structure

```
article-crud-api/
├── create_table.sql        # SQL script to create database and table
├── server.js               # Main Node.js server file with API endpoints
├── package.json            # NPM project configuration
├── .env.example            # Example environment variables (do not commit real credentials)
└── README.md               # Project documentation
```

---

## Notes

* Use `.env` file to keep sensitive database credentials secure.
* Make sure MySQL server is running before starting the backend server.
* API uses async/await for asynchronous database operations.
* Validate your request data before sending to avoid errors.

---

