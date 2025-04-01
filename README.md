## What's Inside

This project is split into two main parts, so it's easy to keep things organized:

*   `frontend/`: This is where all the React code lives. It's responsible for the user interface and talking to the backend.
*   `backend/`: This is the Node.js server that handles the authentication logic and talks to the database.

## Frontend - The Pretty Face

The frontend is all about giving the user a smooth and secure login experience. I used some cool technologies to make it happen:

### Tech I Used

*   **React:** For building the UI, of course!
*   **TypeScript:** To keep everything type-safe and avoid those pesky runtime errors.
*   **Zod:** For validating the login form data. Gotta make sure that email looks like an email, right?
*   **React Hook Form:** Makes managing the form a breeze.
*   **React Query:** Handles all the data fetching and caching from the backend.
*   **Axios:** To make those HTTP requests to the backend.
*   **React Router:** For navigating between the login page and (eventually) a dashboard.

### Getting It Running

First, you'll need to get inside the frontend directory:

cd frontend

Then, install all the necessary packages:

npm install


Finally, start the development server:

npm start


Open your browser and head to `http://localhost:3000` (or whatever port it tells you). You should see the login form!

## Backend - The Brains of the Operation

The backend is where all the magic happens. It's responsible for authenticating users, storing their credentials (securely, of course), and sending back a token.

### Tech I Used

*   **Node.js:** The runtime environment.
*   **TypeScript:** Again, for type safety. Can't get enough of that!
*   **Express:** A lightweight framework for creating the API.
*   **Prisma:** For talking to the database (PostgreSQL). It makes working with databases so much easier!
*   **PostgreSQL:** The database itself. Super reliable and scalable.
*   **Bcrypt:** For hashing passwords. Never store passwords in plain text!
*   **JSON Web Token (JWT):** For creating secure authentication tokens.
*   **Cors:** For handling cross-origin requests. Allows the frontend to talk to the backend.

### Setting It Up

First, get inside the backend directory:

cd backend


Then, install all the packages:

npm install
create a .env file and add database URL JWT_SECRET KEY

**Important:** Replace the placeholder values with your actual database connection string and a strong, random JWT secret key. And seriously, 
Finally, run the Prisma migrations to create the database schema:

npx prisma migrate dev --name init
npx prisma generate


### Running the Backend

To start the backend server, run:

npm run dev


The server should start running on port 5000 (or whatever you set in your `.env` file).

## Error Handling - Because Things Go Wrong

I've implemented error handling on both the frontend and backend to make sure the app is resilient and user-friendly:

*   **Frontend:** If the API returns an error, the frontend displays a helpful message to the user. I also use React Hook Form and Zod to validate the login form and show inline error messages.
*   **Backend:** The backend uses custom error handling middleware to catch errors and return appropriate HTTP status codes and error messages.
