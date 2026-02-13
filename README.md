# Welcome to CivicResolve! 🌟

Hello! This guide will help you get the **CivicResolve** project up and running on your local machine. We've set everything up to work smoothly with a local development environment.

## 📋 Prerequisites

Before we start, make sure you have the following installed on your computer:

*   **Java JDK 17** or higher ☕
*   **Maven** (for building the backend) 🛠️
*   **Node.js** & **npm** (for the frontend) 📦
*   **MySQL Server** (for the database) 🗄️

---

## 🚀 Getting Started

Follow these steps to bring the application to life!

### Step 1: Database Setup 🗄️

1.  Open your MySQL Workbench or command line.
2.  Create a database named `civic_demp`:
    ```sql
    CREATE DATABASE civic_demp;
    ```
3.  The application is configured to use the username `root` and password `Sumit@123` on port `3307`.
    *   *If your settings are different, please update* `Backend/civicresolve-backend/src/main/resources/application.properties`.

### Step 2: backend Setup (Spring Boot) ⚙️

1.  Navigate to the backend directory:
    ```bash
    cd Backend/civicresolve-backend
    ```
2.  Run the application:
    ```bash
    mvn spring-boot:run
    ```
3.  Wait for the logs to show "Started CivicResolveApplication". The backend is now running on **port 8080**.

### Step 3: Frontend Setup (React + Vite) 🎨

1.  Open a new terminal and navigate to the frontend directory:
    ```bash
    cd Frontend/civicresolve-frontend
    ```
2.  Install the dependencies (if you haven't already):
    ```bash
    npm install
    ```
3.  **Important**: Configure your Google Client ID!
    *   Create a file named `.env` in this directory (if it doesn't exist).
    *   Add your Google Client ID:
        ```env
        VITE_GOOGLE_CLIENT_ID=your-google-client-id-here
        ```
    *   *Need an ID?* Go to the [Google Cloud Console](https://console.cloud.google.com/), create an OAuth Client ID for a Web Application, and add `http://localhost:5173` to your Authorized JavaScript Origins.

4.  Start the development server:
    ```bash
    npm run dev
    ```
5.  The frontend is now running on **port 5173**.

---

## 🌍 Accessing the Application

Once both servers are running, open your favorite browser and visit:

👉 **[http://localhost:5173](http://localhost:5173)**

The frontend will automatically talk to the backend at `http://localhost:8080` via a proxy.

---

## ❓ Troubleshooting

*   **Port 8080 or 5173 is already in use?**
    *   Make sure no other services are running on these ports. You can stop them or change the ports in `application.properties` (backend) and `vite.config.js` (frontend).
*   **Database connection failed?**
    *   Double-check your MySQL username, password, and port in `application.properties`.
*   **Login not working?**
    *   Ensure your Google Client ID is correct in the `.env` file and that you've allowed `http://localhost:5173` in your Google Cloud Console.

Happy Coding! 🎉
