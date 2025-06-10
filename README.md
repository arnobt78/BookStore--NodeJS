# BookStore -- NodeJS

BookStore is a full-stack sample web application designed to demonstrate CRUD operations for a book management system. The app allows users to add, view, filter, and remove books from a MongoDB database by genre. Built as a learning project, it integrates a Node.js/Express REST API backend with an AngularJS client, providing a modern, responsive web experience.

---

## Table of Contents

- [Project Details](#project-details)
- [Features](#features)
- [Screenshots](#screenshots)
- [Keywords & Technologies](#keywords--technologies)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Contributing](#contributing)
- [License](#license)

---

## Project Details

BookStore provides a simple, easy-to-use interface for managing a collection of books, categorized by genre. The backend is built with Node.js and Express, offering RESTful APIs for CRUD operations. The frontend, developed with AngularJS, communicates with the backend to present a dynamic, single-page application (SPA) experience.

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

## Screenshots

<!-- Screenshot images from the current README (please ensure these images are still present in your repo) -->

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

Typical structure of this project:

```
BookStore--NodeJS/
│
├── app.js                  # Main application entry (Express server)
├── package.json            # Project metadata and dependencies
├── README.md               # Project documentation
├── models/                 # Mongoose models (Book schema)
├── client/                 # AngularJS frontend app
│   ├── bower_components/   # Frontend dependencies
│   ├── css/                # Stylesheets
│   ├── js/                 # AngularJS app, controllers, services
│   └── index.html          # Main HTML file
└── ...
```

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

- **Sample Payload for POST /api/books:**
  ```json
  {
    "title": "Book Title",
    "author": "Author Name",
    "genre": "Fiction"
  }
  ```

---

## Contributing

Contributions, issues, and feature requests are welcome!  
Feel free to submit a pull request or open an issue.

---

## License

This project is open source and available under the MIT License.

---

> _Happy coding, and enjoy exploring the BookStore project!_
