# SEA CINEMA API

This is a payment API for SEA CINEMA, built using Node.js and Express.

## Prerequisites

- Node.js installed on your machine
- Firebase project with Firestore enabled
- Midtrans payment gateway account

## Getting Started

1. Clone the repository:

```
git clone https://github.com/codeyzx/sea-cinema-api.git
```

2. Install dependencies:

```
cd sea-cinema-api
```

```
npm install
```

3. Set up environment variables:

- Create a `.env` file in the root directory.
- Add the following environment variables to the `.env` file:

  ```
  apiKey=YOUR_FIREBASE_API_KEY
  authDomain=YOUR_FIREBASE_AUTH_DOMAIN
  projectId=YOUR_FIREBASE_PROJECT_ID
  storageBucket=YOUR_FIREBASE_STORAGE_BUCKET
  messagingSenderId=YOUR_FIREBASE_MESSAGING_SENDER_ID
  appId=YOUR_FIREBASE_APP_ID
  SERVER_KEY=YOUR_MIDTRANS_SERVER_KEY
  CLIENT_KEY=YOUR_MIDTRANS_CLIENT_KEY
  ```

  Replace `YOUR_FIREBASE_API_KEY`, `YOUR_FIREBASE_AUTH_DOMAIN`, etc. with your actual Firebase project and Midtrans API credentials.

4. Start the server:

```
npm start
```

The server will start running on http://localhost:3000.

5. Access the API documentation:

   Open http://localhost:3000/api-docs in your browser to view the Swagger UI documentation.

## API Endpoints

### Create a new transaction token

- URL: `/charge`
- Method: POST
- Request Body: JSON object containing customer and item details (refer to API documentation for schema)
- Response: JSON object with a transaction token

### Handle payment notifications

- URL: `/notification_handler`
- Method: POST
- Request Body: JSON object containing transaction status information from the payment gateway
- Response: JSON object with the updated transaction status
