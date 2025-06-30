# BookStore - Node.js

BookStore is a full-stack sample web application designed to demonstrate CRUD operations for a book management system. The app allows users to add, view, filter, and remove books from a MongoDB database with a clean, responsive AngularJS frontend and a robust Node.js/Express backend.

---

## Table of Contents

- [Project Summary](#project-summary)
- [Project Details](#project-details)
- [Features](#features)
- [Screenshots](#screenshots)
- [Keywords & Technologies](#keywords--technologies)
- [Project Structure](#project-structure)
- [Component Overview](#component-overview)
- [How It Works: Walkthrough](#how-it-works-walkthrough)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Code Examples](#code-examples)
- [Contributing](#contributing)
- [License](#license)
- [Conclusion](#conclusion)

---

## Project Summary

**BookStore--NodeJS** is a CRUD-based educational project for managing a collection of books. It is an excellent resource for learning modern web development with the MEAN (MongoDB, Express.js, AngularJS, Node.js) stack. The project covers backend API design, database modeling with Mongoose, frontend development with AngularJS, and integration of RESTful services.

**Educational Goals:**
- Teach how to build and structure a full-stack application
- Demonstrate practical database interactions (CRUD)
- Show how to build RESTful APIs and consume them with a frontend
- Introduce modular code organization and MVC concepts

---

## Project Details

BookStore provides a simple, easy-to-use interface for managing a collection of books, categorized by genre. The backend is built with Node.js and Express, offering RESTful APIs for CRUD operations. The frontend is developed in AngularJS for a dynamic, interactive user experience, with MongoDB as the persistent data store.

**Key Concepts:**
- Modular codebase using MVC design
- RESTful API endpoints
- AngularJS data binding and services
- Real-world CRUD flows
- Simple, extensible, and beginner-friendly

---

## Features

- **Add New Books:** Enter details and assign a genre to add books to the database.
- **View Book List:** See all books currently in the system, with support for genre-based filtering.
- **Remove Books:** Delete books directly from the list.
- **Genre Filtering:** Filter books by their respective genres.
- **RESTful API:** Backend exposes endpoints for managing books.
- **Responsive UI:** AngularJS frontend for a dynamic and user-friendly interface.
- **MongoDB Integration:** Persistent storage of book data.
- **Simple, Extensible Codebase:** Designed for easy learning and extension.

---

## Keywords & Technologies

**Backend:**
- Node.js
- Express.js
- MongoDB
- Mongoose (ODM)

**Frontend:**
- AngularJS
- HTML5
- CSS3
- JavaScript

**Other:**
- REST API
- MVC Architecture
- CRUD Operations

---

## Project Structure

A typical structure of this project:

```
BookStore--NodeJS/
│
├── app.js                  # Main application entry (Express server)
├── package.json            # Project metadata and dependencies
├── README.md               # Project documentation
├── models/                 # Mongoose models (Book and Genre schemas)
├── client/                 # AngularJS frontend app
│   ├── bower_components/   # Frontend dependencies
│   ├── css/                # Stylesheets
│   ├── js/                 # AngularJS app, controllers, services
│   ├── controllers/        # AngularJS controllers
│   ├── views/              # HTML partials (views)
│   └── index.html          # Main HTML file
└── ...
```

- **app.js:** Sets up the Express server, connects to MongoDB, and defines API routes.
- **models/:** MongoDB data models (Book, Genre).
- **client/:** All frontend code, separated by concerns (controllers, views, styles).

---

## Component Overview

### Backend

- **app.js:** Main server file. Sets up Express, connects to MongoDB, configures middleware, and defines API routes.
- **models/book.js:** Mongoose schema/model for books.
- **models/genre.js:** Mongoose schema/model for genres.

### Frontend

- **client/index.html:** Entry point for the AngularJS app.
- **client/app.js:** AngularJS app module, routing configuration.
- **client/controllers/:** AngularJS controllers for managing app logic (e.g., BookController).
- **client/views/:** HTML templates for different views (book list, add book form, etc.).
- **client/css/:** Stylesheets for the frontend.

---

## How It Works: Walkthrough

### 1. **Launching the App**
- Start the backend Express server (`node app.js`), which connects to MongoDB.
- Open the frontend app in a browser (`http://localhost:3000`).

### 2. **Adding a Book**
- Use the "Add Book" form to enter the title, author, and genre.
- On submit, AngularJS sends a POST request to `/api/books`.
- The backend validates, saves the book using Mongoose, and returns the updated list.

### 3. **Viewing & Filtering Books**
- Book list is fetched from the backend (`GET /api/books`).
- Use dropdown to filter by genre. AngularJS updates the displayed list dynamically.

### 4. **Deleting a Book**
- Click the delete/remove button next to a book.
- AngularJS sends a DELETE request to `/api/books/:id`.
- Backend removes the book from MongoDB and returns success.

### 5. **API Interaction**
- You can use tools like Postman to interact directly with the API for learning/testing.

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v12+ recommended)
- [MongoDB](https://www.mongodb.com/) (running locally or accessible remotely)
- [npm](https://www.npmjs.com/)

### Installation

1. **Clone the repository:**
    ```bash
    git clone https://github.com/arnobt78/BookStore--NodeJS.git
    cd BookStore--NodeJS
    ```

2. **Install dependencies:**
    ```bash
    npm install
    ```

3. **(Optional) Configure MongoDB connection:**
    - By default, the app connects to a local MongoDB instance.
    - To use a different database, update the MongoDB URI in `app.js` or your configuration file.

4. **Start MongoDB:**
    - Make sure MongoDB is running before starting the app.

5. **Run the application:**
    ```bash
    node app.js
    ```

6. **Access the app:**
    - Open your browser and navigate to `http://localhost:3000` (or the port specified in your app).

---

## Usage

- **Add Book:** Use the "Add Book" form—enter title, author, genre, and submit.
- **View Books:** All books appear in the list. Filter by genre using the dropdown.
- **Remove Book:** Click the delete/remove button next to a book entry.
- **API:** You can also interact with the backend endpoints directly using tools like Postman.

---

## API Endpoints

| Method | Endpoint        | Description              |
|--------|----------------|--------------------------|
| GET    | /api/books     | List all books           |
| POST   | /api/books     | Add a new book           |
| DELETE | /api/books/:id | Delete a book by ID      |

**Sample Payload for POST /api/books:**
```json
{
  "title": "Book Title",
  "author": "Author Name",
  "genre": "Fiction"
}
```

---

## Code Examples

### Example Mongoose Model (models/book.js)
```js
const mongoose = require('mongoose');
const bookSchema = mongoose.Schema({
  title: { type: String, required: true },
  author: String,
  genre: String
});
module.exports = mongoose.model('Book', bookSchema);
```

### Example Express Route (app.js)
```js
const Book = require('./models/book');
app.get('/api/books', (req, res) => {
  Book.find({}, (err, books) => {
    if (err) res.status(500).send(err);
    else res.json(books);
  });
});
```

### Example AngularJS Service (client/js/services/bookService.js)
```js
app.factory('BookService', function($http) {
  return {
    getBooks: function() {
      return $http.get('/api/books');
    },
    addBook: function(book) {
      return $http.post('/api/books', book);
    },
    deleteBook: function(id) {
      return $http.delete('/api/books/' + id);
    }
  };
});
```

### Example AngularJS Controller (client/controllers/BookController.js)
```js
app.controller('BookController', function($scope, BookService) {
  $scope.books = [];
  $scope.getBooks = function() {
    BookService.getBooks().then(res => {
      $scope.books = res.data;
    });
  };
  $scope.addBook = function() {
    BookService.addBook($scope.newBook).then(() => {
      $scope.getBooks();
      $scope.newBook = {};
    });
  };
  $scope.deleteBook = function(id) {
    BookService.deleteBook(id).then(() => $scope.getBooks());
  };
  $scope.getBooks();
});
```

---

## Contributing

Contributions, issues, and feature requests are welcome!  
Feel free to submit a pull request or open an issue.

---

## License

This project is open source and available under the MIT License.

---

## Conclusion

BookStore--NodeJS is a hands-on, beginner-friendly full-stack project that demonstrates modern web development best practices. It’s ideal for learners and educators alike to understand how backend and frontend communicate, how databases are modeled, and how to organize a maintainable codebase.

---

> _Happy Coding!_ 🎉  
> Thank you for exploring and sharing the BookStore project!
