# Book Management REST API

A simple REST API built using **Node.js** and **Express.js** to manage a list of books.

This project implements CRUD operations:

- Create a book
- Read books
- Update a book
- Delete a book

The data is stored in an **in-memory array**, so the data will reset whenever the server is restarted.

---

## Technologies Used

- Node.js
- Express.js
- Postman
- JavaScript

---

## Project Structure

```text
day3/
│
├── server.js
├── package.json
├── package-lock.json
└── README.md


---------------------------------------------------------------
Installation
1. Clone or open the project

Open the project folder in VS Code.

2. Initialize Node.js
npm init -y
3. Install Express
npm install express
Running the Server

Start the server using:

node server.js

The server will run at:

http://localhost:3000

You should see:

Server running at http://localhost:3000
API Endpoints
1. GET - Get All Books
Request
GET http://localhost:3000/books
Description

Returns all books currently stored in the array.

Example Response
[
  {
    "id": 1,
    "title": "The Alchemist",
    "author": "Paulo Coelho"
  },
  {
    "id": 2,
    "title": "Wings of Fire",
    "author": "A.P.J. Abdul Kalam"
  }
]
2. POST - Add a New Book
Request
POST http://localhost:3000/books
Body

Select:

Body → raw → JSON

Example:

{
  "title": "Rich Dad Poor Dad",
  "author": "Robert Kiyosaki"
}
Example Response
{
  "message": "Book added successfully",
  "book": {
    "id": 3,
    "title": "Rich Dad Poor Dad",
    "author": "Robert Kiyosaki"
  }
}
3. PUT - Update a Book
Request

Use the book ID in the URL.

PUT http://localhost:3000/books/3
Body

Select:

Body → raw → JSON

Example:

{
  "title": "Rich Dad Poor Dad - Updated",
  "author": "Robert Kiyosaki"
}
Example Response
{
  "message": "Book updated successfully",
  "book": {
    "id": 3,
    "title": "Rich Dad Poor Dad - Updated",
    "author": "Robert Kiyosaki"
  }
}
4. DELETE - Delete a Book
Request
DELETE http://localhost:3000/books/3

Replace 3 with the ID of the book you want to delete.

Example Response
{
  "message": "Book deleted successfully",
  "book": {
    "id": 3,
    "title": "Rich Dad Poor Dad - Updated",
    "author": "Robert Kiyosaki"
  }
}
Error Handling

The API handles common errors.

Book Not Found

If a book ID does not exist:

{
  "message": "Book not found"
}

The API returns:

404 Not Found
Missing Title or Author

If title or author is missing when creating or updating a book:

{
  "message": "Title and author are required"
}

The API returns:

400 Bad Request
Testing with Postman

The API was tested using Postman.

The following operations were tested successfully:

✅ GET /books
✅ POST /books
✅ PUT /books/:id
✅ DELETE /books/:id
CRUD Summary
Operation	HTTP Method	Endpoint
Get all books	GET	/books
Add a book	POST	/books
Update a book	PUT	/books/:id
Delete a book	DELETE	/books/:id
Important Note

This project uses an in-memory JavaScript array to store books.

Therefore, any books added, updated, or deleted will be lost when the Node.js server is stopped or restarted.

For a real-world application, a database such as MongoDB, MySQL, or PostgreSQL would normally be used.

Conclusion

This project demonstrates how to build a basic REST API using Node.js and Express.js.

It covers the four main CRUD operations:

Create → Read → Update → Delete

The API can be tested using Postman at:

http://localhost:3000

### 📁 Where to put it

Inside your `day3` folder:

```text
day3
├── server.js
├── package.json
├── package-lock.json
└── README.md

Save the file as exactly README.md.