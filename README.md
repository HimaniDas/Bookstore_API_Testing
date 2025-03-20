# 📚 Book Store API Testing - Postman Collection

This Postman collection is designed to test the Book Store API provided by `https://bookstore.demoqa.com`. The collection includes various API requests to interact with the Book Store API, such as listing books, creating users, generating tokens, assigning books to users, and checking authorization.

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

## 📚 Collection Details

- **Collection Name**: `Book Store API Testing`
- **Base URL**: `https://bookstore.demoqa.com`
- **Environment Variables**: None required (but can be added if needed).

## 📌 API Endpoints Covered

1. **Book Listing**:
   - **Method**: `GET`
   - **Endpoint**: `/BookStore/v1/Books`
   - **Description**: Retrieves a list of all books available in the store.

2. **Create User**:
   - **Method**: `POST`
   - **Endpoint**: `/Account/v1/User`
   - **Description**: Creates a new user with a username and password.
   - **Request Body**:
     ```json
     {
       "userName": "your_name",
       "password": "your_password"
     }
     ```

3. **Generate Token**:
   - **Method**: `POST`
   - **Endpoint**: `/Account/v1/GenerateToken`
   - **Description**: Generates a token for the user to authenticate subsequent requests.
   - **Request Body**:
     ```json
     {
       "userName": "your_name",
       "password": "your_password"
     }
     ```

4. **Assign Books to User**:
   - **Method**: `POST`
   - **Endpoint**: `/BookStore/v1/Books`
   - **Description**: Assigns books to a user by their ISBNs.
   - **Authentication**: Basic Auth (username: `...`, password: `...`)
   - **Request Body**:
     ```json
     {
       "userId": "3a4baa55-bc47-4e1f-83f1-bd1120b577ff",
       "collectionOfIsbns": [
         {
           "isbn": "first_book_isbn"
         },
         {
           "isbn": "second_book_isbn"
         }
       ]
     }
     ```

5. **View Logging Model (Authorization Check)**:
   - **Method**: `POST`
   - **Endpoint**: `/Account/v1/Authorized`
   - **Description**: Checks if the user is authorized using a bearer token.
   - **Authentication**: Bearer Token (provided in the request).
   - **Request Body**:
     ```json
     {
       "userName": "your_name",
       "password": "your_password"
     }
     ```

## 📝 Notes

- Ensure that the API is up and running before running the tests.
- Replace placeholder values (e.g., `userId`, `isbn`) with actual values when testing.
- The bearer token used in the "View Logging Model" request is a placeholder. Replace it with a valid token generated from the "Generate Token" request.
