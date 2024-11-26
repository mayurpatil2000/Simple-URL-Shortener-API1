


## **Installation and Setup**

### **Prerequisites**
Before running the application, ensure you have the following software installed:

- **Node.js** (v14 or later)
- **MongoDB** (local or cloud instance)
- **Package manager** (npm or yarn)

### **Steps to Run Locally**

1. **Clone the repository:**

   ```bash
   git clone https://github.com/mayurpatil2000/Simple-URL-Shortener-API1
   ```

2. **Navigate into the project directory:**

   ```bash
   cd Simple-URL-Shortener-API1
   ```

3. **Install dependencies:**

   ```bash
   npm install
   ```

4. **Create an `.env` file** in the root of the project directory and add the following environment variables:

   ```bash
   MONGO_URI=mongodb://localhost:27017/short-url
   PORT=8001
   ```

   - **MONGO_URI**: URL to your MongoDB instance (local or cloud).
   - **PORT**: The port on which the application will run.

5. **Start the MongoDB server** (if using a local instance).

   If you're using MongoDB locally, ensure it's running on the specified URI.

6. **Start the application:**

   ```bash
   npm start
   ```

   The application will run at `http://localhost:8001`.

---

## **API Endpoints**

### 1. **POST /url**
- **Description**: Generate a short URL from a provided long URL.
  
- **Request Body**:

   ```json
   {
       "url": "https://example.com"
   }
   ```

- **Response**:

   ```json
   {
       "id": "shortId123"
   }
   ```

- **Errors**:

   - **400 Bad Request**: If the URL is missing.
   - **500 Internal Server Error**: If an unexpected server error occurs.

---

### 2. **GET /:shortId**
- **Description**: Redirects to the original URL using the shortened URL ID.

- **Path Parameters**:
   - `shortId`: The shortened URL ID.

- **Response**:
   - Redirects the user to the original URL.

- **Errors**:
   - **404 Not Found**: If the short URL is not found.
   - **500 Internal Server Error**: If an unexpected server error occurs.

---

### 3. **GET /url/analytics/:shortId**
- **Description**: Fetch usage statistics for a shortened URL, including the number of clicks and the timestamp of each visit.

- **Path Parameters**:
   - `shortId`: The shortened URL ID.

- **Response**:

   ```json
   {
       "totalClicks": 10,
       "analytics": [
           { "timestamp": 1699999999 },
           { "timestamp": 1700000000 }
       ]
   }
   ```

- **Errors**:
   - **404 Not Found**: If the short URL is not found.
   - **500 Internal Server Error**: If an unexpected server error occurs.

---
