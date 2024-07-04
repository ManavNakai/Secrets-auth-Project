# Secrets-auth-Project
Secrets-auth-Project is a website that allows users to log in using local or Google OAuth login. After signing up/logging in, users can submit their private secrets, which are only visible to them. Users can log out if they want, or their session details will be saved to their local browser. This project focuses on user authorization and session handling using various technologies.

## Table of Contents
- [Tech-Stack and Tools Used](#tech-stack-and-tools-used)
- [Features](#features)
- [Getting Started](#getting-started)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Tech-Stack and Tools Used
- **CSS3**: For styling the web page.
- **Node.js**: For setting up the backend server.
- **Express.js**: For managing server-side logic and routing.
- **EJS**: For rendering dynamic content on the web page.
- **PostgreSQL**: For storing and managing user data and secret.
- **PG Admin**: For managing the PostgreSQL database.
- **bcrypt**: For hashing passwords.
- **passportjs**: For authentication.
- **passport-local**: For local authentication strategy.
- **passport-google-oauth2**: For Google OAuth authentication strategy.
- **express-session**: For session management.
- **dotenv**: For managing environment variables.

## Features
- **User Authentication**: Allows users to sign up and log in using local authentication or Google OAuth.
- **Session Management**: User sessions are maintained across browser sessions.
- **Secret Submission**: Users can submit private secrets visible only to them.
- **User Logout**: Users can log out, clearing their session data.

## Getting Started
To get a local copy up and running, follow these simple steps:

### Prerequisites
- Node.js installed on your local machine
- PostgreSQL installed and configured
- PG Admin installed for database management
- A code editor (e.g., VSCode)
- Google Cloud account for OAuth setup

### Installation
1. Clone the repository:
   ```sh
   git clone https://github.com/ManavNakai/Secrets-auth-Project.git
   ```
2. Navigate to the project directory:
   ```sh
   cd Secrets-auth-Project
   ```
3. Install the required dependencies:
   ```sh
   npm install
   ```
   
4. Set up the PostgreSQL database `secrets` locally using PG Admin and create the `users` table:
   
   4.1. **Open PG Admin and create a new database**:
   
   - Open PG Admin and create a new database named `secrets`.
     
   4.2. **Create the `users` table**:
   
   - Create a table named `users` with the following structure:
     
     ```sql
     CREATE TABLE users (
       id SERIAL PRIMARY KEY,
       email VARCHAR(100) UNIQUE NOT NULL,
       password VARCHAR(100) NOT NULL,
       secret TEXT
     );
     ```

5. Set up Google OAuth credentials:
   
   5.1. **Go to the [Google Cloud Console](https://console.cloud.google.com/) and Log in with your Google Account**.
   
   5.2. **Create a new project named "Secrets"**.
   
   5.3. **Navigate to "APIs & Services" and create OAuth 2.0 Client IDs**.
   
   5.4. **Add your authorized redirect URLs (e.g., `http://localhost:3000/auth/google/secrets`)**.
   
   5.5. **Copy the Client ID and Client Secret and add them to your `.env` file**.

7. Create a `.env` file in the project root and add your PostgreSQL database connection details along with session and Google OAuth credentials:
   
   ```plaintext
   PG_USER=your_db_user
   PG_HOST="localhost"
   PG_DATABASE="secrets"
   PG_PASSWORD=your_db_password
   PG_PORT="5432"
   SESSION_SECRET=your_session_secret
   GOOGLE_CLIENT_ID=your_google_client_id
   GOOGLE_CLIENT_SECRET=your_google_client_secret
   ```

8. Start the server:
   ```sh
   node index.js
   ```

9. Open your web browser and go to `http://localhost:3000`.

## Usage
- Open your web browser and navigate to `http://localhost:3000`.
- Sign up or log in using your email and password or Google account.
- Submit your private secret after logging in.
- View your secret or log out as needed.

## Contributing
Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have suggestions for improving the project, please follow these steps:
1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License
Distributed under the MIT License. See `LICENSE` for more information.

## Contact
Project Link: [https://github.com/ManavNakai/Secrets-auth-Project](https://github.com/ManavNakai/Secrets-auth-Project)

---

Thank you for checking out the Secrets-auth-Project! Feel free to reach out if you have any questions or need further assistance.
