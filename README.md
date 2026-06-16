# Mugisha's Book Store API

A simple REST API built with Express and MongoDB (Mongoose) to manage books for Mugisha's book store in Kigali.

## Setup

1. Install dependencies:
   ```
   npm install
   ```

2. Update `.env` if needed (defaults to a local MongoDB instance):
   ```
   MONGO_URI=mongodb://localhost:27017/mugisha_bookstore
   PORT=3000
   ```
   If you're using MongoDB Atlas, replace `MONGO_URI` with your connection string, e.g.
   `mongodb+srv://<user>:<password>@cluster.mongodb.net/mugisha_bookstore`

3. Start the server:
   ```
   npm start
   ```
   or, for auto-reload during development:
   ```
   npm run dev
   ```

## Book Model

| Field  | Type   | Required |
|--------|--------|----------|
| title  | String | Yes      |
| author | String | Yes      |
| price  | Number | Yes      |

## Endpoints

| Method | Route             | Description              |
|--------|-------------------|--------------------------|
| POST   | /api/books        | Add a new book            |
| GET    | /api/books        | Get all books             |
| GET    | /api/books/:id    | Get a single book by ID   |
| PUT    | /api/books/:id    | Update a book by ID       |
| DELETE | /api/books/:id    | Delete a book by ID       |

`GET /api/books/:id`, `PUT /api/books/:id`, and `DELETE /api/books/:id` return `404` if the book isn't found.

### Example request body (POST/PUT)

```json
{
  "title": "Things Fall Apart",
  "author": "Chinua Achebe",
  "price": 12000
}
```

## Pushing to GitHub

```
git init
git add .
git commit -m "Initial commit: Book store API"
git branch -M main
git remote add origin <your-repo-url>
git push -u origin main
```

> Note: this project's `.env` is committed as-is so it's ready to run immediately, but in general it's good practice to keep real credentials (e.g. Atlas passwords) out of version control — add `.env` to `.gitignore` and share secrets separately once you connect to a real database.
