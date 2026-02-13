# 👋 Welcome to the CivicResolve Project!

Hi there! We are so excited to have you here. This document is your friendly guide to getting **CivicResolve** up and running on your local machine. Think of this as a recipe for setting up your development environment—just follow the steps, and you'll be cooking with code in no time! 🍳✨

---

## �️ What You'll Need

Before we dive in, let's make sure you have the essentials ready. It's like checking for ingredients before baking a cake:

*   **Java JDK 17** (or newer) ☕ - The backbone of our backend.
*   **Maven** 🛠️ - To help build and run the Spring Boot app.
*   **Node.js & npm** 📦 - To bring our React frontend to life.
*   **MySQL Server** 🗄️ - Where all our data lives happily.

---

## 🚀 Let's Get Started!

Ready? Let's get this show on the road. Follow these three simple steps:

### Step 1: Solving the Database Puzzle 🧩

First, we need a place to store our data.
1.  Fire up **MySQL Workbench** or your favorite database tool.
2.  Run this simple command to create the database:
    ```sql
    CREATE DATABASE civic_demp;
    ```
3.  **Note**: By default, we look for a user named `root` with the password `Sumit@123` running on port `3307`.
    *   *Got different settings?* No worries! Just peek into `Backend/civicresolve-backend/src/main/resources/application.properties` and update them to match your setup.

### Step 2: Waking up the Backend (Spring Boot) 🌱

Now, let's start the engine.
1.  Open your terminal and hop into the backend folder:
    ```bash
    cd Backend/civicresolve-backend
    ```
2.  Tell Maven to run the app:
    ```bash
    mvn spring-boot:run
    ```
3.  Give it a moment... once you see "Started CivicResolveApplication", you're golden! The backend is listening for you on **port 8080**.

### Step 3: Lighting up the Frontend (React) ✨

Finally, let's see the beautiful UI.
1.  Open a **new** terminal window (keep the other one running!) and go to the frontend:
    ```bash
    cd Frontend/civicresolve-frontend
    ```
2.  If this is your first time here, let's install the packages:
    ```bash
    npm install --legacy-peer-deps
    ```
3.  **🔑 Key Step**: We need a Google Client ID for logins to work.
    *   Create a file named `.env` in this folder.
    *   Paste your ID inside like this:
        ```env
        VITE_GOOGLE_CLIENT_ID=your-google-client-id-here
        ```
    *   *Don't have one?* You can grab one from the [Google Cloud Console](https://console.cloud.google.com/). Just remember to allow `http://localhost:5173`!

4.  Launch the site:
    ```bash
    npm run dev
    ```
5.  Success! The frontend is alive and running on **port 5173**.

---

## � You're In!

Go ahead and open your browser to:

👉 **[http://localhost:5173](http://localhost:5173)**

Everything is connected automatically. You don't need to worry about the backend URL; the frontend knows exactly where to find it.

---

## 🚑 Stuck? Here's some help.

Sometimes things don't go exactly as planned, and that's okay!
*   **"Port already in use?"** - Maybe you have another app running? You can shut it down or change the ports in our config files.
*   **"Database error?"** - it happens! Double-check that username and password in the backend properties file.
*   **"Login failing?"** - It's usually the Google Client ID. Check the `.env` file and make sure Google knows about `localhost:5173`.

**Happy Coding!** We hope you build something amazing with CivicResolve. 🚀
