Installation and Setup
Prerequisites
Node.js (v14 or later).
MongoDB (local or cloud instance).
Package manager (npm or yarn).
Steps to Run Locally
Clone the repository:



git clone https://github.com/mayurpatil2000/Simple-URL-Shortener-API1
cd Simple-URL-Shortener-API1


Install dependencies:
npm install


Create an .env file for environment variables:

MONGO_URI=mongodb://localhost:27017/
PORT=8001
Start the MongoDB server (if using a local instance).

Start the application:
npm start

The application will run at http://localhost:8001.


API Endpoints

1. POST /url
Description: Generate a short URL.

Request Body:

json
Copy code
{
    "url": "https://example.com"
}
Response:

json
Copy code
{
    "id": "shortId123"
}
Errors:

400 Bad Request: URL is missing.
500 Internal Server Error: Unexpected server error.


2. GET /:shortId

Description: Redirect to the original URL.

Path Parameters:

shortId: The shortened URL ID.
Response:

Redirects the user to the original URL.
Errors:

404 Not Found: Short URL not found.
500 Internal Server Error: Unexpected server error.



3. GET /url/analytics/:shortId

Description: Fetch usage statistics for a shortened URL.

Path Parameters:

shortId: The shortened URL ID.
Response:

json
Copy code
{
    "totalClicks": 10,
    "analytics": [
        { "timestamp": 1699999999 },
        { "timestamp": 1700000000 }
    ]
}
Errors:

404 Not Found: Short URL not found.
500 Internal Server Error: Unexpected server error.




