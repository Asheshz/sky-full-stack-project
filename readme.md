<!-- Sky App - Full-Stack Authentication Application: Setup -->
This guide provides the necessary steps to set up and run the full-stack authentication application locally.

Prerequisites
To run this project, you'll need the following installed:

Node.js (v14 or higher)

MongoDB Atlas account (free tier is sufficient)

npm or yarn

1. MongoDB Atlas Setup
The application uses MongoDB for data persistence. You must set up a connection string from MongoDB Atlas.

Create a Cluster: Sign up/Log in to MongoDB Atlas and create a new FREE tier (M0 Sandbox) cluster.

Create Database User: In the Atlas dashboard, go to "Database Access" and create a new database user (save the username and password).

Configure Network Access: Go to "Network Access" and add your current IP address, or for development, choose "Allow Access from Anywhere".

Get Connection String: Go to "Database", click "Connect" on your cluster, choose "Connect your application", and copy the connection string. It will look like this:

mongodb+srv://<username>:<password>@clustername.mongodb.net/sky-app?retryWrites=true&w=majority
Remember to replace <username> and <password> with your database user credentials.

2. Backend Setup
The backend is built with Node.js and Express.

Bash

# Navigate to the backend directory
cd backend

# Install necessary dependencies
npm install

# Create the .env file
# Paste your MongoDB connection string and set a JWT secret.
echo "MONGODB_URI=mongodb+srv://username:password@clustername.mongodb.net/sky-app?retryWrites=true&w=majority
PORT=3001
JWT_SECRET=your-super-secret-jwt-key-change-this-in-production" > .env

# Start the backend server
npm run dev
The backend server will run on http://localhost:3001.

3. Frontend Setup
The frontend is a Next.js application.

Bash

# Navigate to the frontend directory
cd ../frontend

# Install necessary dependencies
npm install

# Create the .env.local file to configure the API URL
echo "NEXT_PUBLIC_API_URL=http://localhost:3001/api" > .env.local

# Start the development server
npm run dev
The frontend application will run on http://localhost:3000.

4. Usage
Ensure both the backend (npm run dev in backend/) and the frontend (npm run dev in frontend/) are running.

Open your browser and go to: http://localhost:3000

You can now Register a new account, Login, and access the Protected Dashboard.

