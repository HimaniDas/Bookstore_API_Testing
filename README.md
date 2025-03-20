# 📚 Book Store API Testing

This project contains a **Postman collection** for testing a **Book Store API**. The API provides functionalities to list books, create users, generate authentication tokens, and assign books to users.

## 📌 Prerequisites

Before using this collection, ensure you have:

- [Postman](https://www.postman.com/downloads/) installed
- Internet access to interact with the API

## 🔧 How to Use

### 1️⃣ Import the Collection
- Open Postman.
- Click on `File > Import`.
- Select and import the `Book Store API Testing_postman_collection.json` file.

### 2️⃣ Set Up Environment (Optional but Recommended)
- Create a new environment in Postman.
- Add the following variables:
  - `baseUrl`: `https://bookstore.demoqa.com`
  - `userName`: Your test username
  - `password`: Your test password
  - `token`: (To be generated after authentication)

### 3️⃣ Run the API Tests
- Use the collection to send requests to the API endpoints.
- Authenticate and obtain a token before accessing secured endpoints.

---

## 📌 API Endpoints

### 📖 1. Book Listing
- **Method:** `GET`
- **URL:** `${baseUrl}/BookStore/v1/Books`
- **Description:** Fetches a list of available books.

### 👤 2. Create User
- **Method:** `POST`
- **URL:** `${baseUrl}/Account/v1/User`
- **Request Body (JSON):**
  ```json
  {
    "userName": "your_username",
    "password": "your_password"
  }
Description: Creates a new user account.

### 🔑 3. Generate Token
Method: POST
URL: ${baseUrl}/Account/v1/GenerateToken
Request Body (JSON):
json
Copy
Edit
{
  "userName": "your_username",
  "password": "your_password"
}
Description: Generates an authentication token for the user.

### 📚 4. Assign Books to User
Method: POST
URL: ${baseUrl}/BookStore/v1/Books
Authentication: Basic Auth (Username & Password)
Request Body (JSON):
json
Copy
Edit
{
  "userId": "your_user_id",
  "collectionOfIsbns": [
    { "isbn": "first_book_isbn" },
    { "isbn": "second_book_isbn" }
  ]
}
Description: Assigns books to a user.

### 🔒 5. View Logging Model (Authorization Check)
Method: POST
URL: ${baseUrl}/Account/v1/Authorized
Authentication: Bearer Token
Request Body (JSON):
json
Copy
Edit
{
  "userName": "your_username",
  "password": "your_password"
}
Description: Verifies if the user is authorized.

### 🚀 Running Tests
You can use Postman’s Runner to test all endpoints sequentially:

Open Postman, select Runner.
Choose the Book Store API Testing collection.
Click Run.

### 📝 Notes
Replace your_username, your_password, and your_user_id with actual values.
Tokens expire after a period; regenerate them as needed.
Some endpoints require authentication.
