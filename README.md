
---

# GitHub OAuth Authentication with Passport.js

This is a simple Express application that uses GitHub OAuth 2.0 for authentication via Passport.js. It allows users to log in with their GitHub account, view a personalized profile page, and log out.

## Features

- GitHub OAuth 2.0 authentication with Passport.js
- Session-based authentication to keep users logged in
- Displays a personalized greeting on the profile page
- Simple login and logout functionality

## Prerequisites

To run this project, you'll need:

- [Node.js](https://nodejs.org/) (version 12 or higher)
- A GitHub OAuth application (to obtain the Client ID and Client Secret)
- A `.env` file to securely manage sensitive information

## Setup Instructions

### Step 1: GitHub OAuth Credentials

1. Go to [GitHub Developer Settings](https://github.com/settings/developers).
2. Click on **New OAuth App**.
3. Configure the application:
   - **Application Name**: Choose any name.
   - **Homepage URL**: `http://localhost:3000`
   - **Authorization Callback URL**: `http://localhost:3000/auth/github/callback`
4. Register the application.
5. Note your **Client ID** and **Client Secret** – you’ll need them in the `.env` file.

### Step 2: Clone the Repository

```bash
git clone https://github.com/sahil352005/your-repo-name.git
cd your-repo-name
```

### Step 3: Install Dependencies

Run the following command to install the necessary dependencies:

```bash
npm install
```

### Step 4: Configure Environment Variables

Create a `.env` file in the root directory of the project and add your GitHub OAuth credentials:

```plaintext
GITHUB_CLIENT_ID=your-client-id
GITHUB_CLIENT_SECRET=your-client-secret
```

### Step 5: Run the Server

Start the server with the following command:

```bash
node index.js
```

The server should now be running at `http://localhost:3000`.

## Routes

- **`/`** - Home page with a "Login with GitHub" link.
- **`/auth/github`** - Initiates GitHub authentication.
- **`/auth/github/callback`** - Callback URL after GitHub authentication.
- **`/profile`** - Displays the user’s GitHub username (only accessible when logged in).
- **`/logout`** - Logs the user out and redirects to the home page.

## How It Works

1. When you navigate to the home page, click the "Login with GitHub" link.
2. GitHub will ask for your permission to share your profile information.
3. After granting permission, you’ll be redirected to the `/profile` page, where you’ll see a welcome message with your GitHub username.
4. Use the `/logout` route to end the session and return to the home page.

## Troubleshooting

- Ensure that the **GitHub Client ID** and **Client Secret** in the `.env` file are correct.
- Confirm that **http://localhost:3000/auth/github/callback** is added as an authorized callback URL in your GitHub Developer Settings.
- If you encounter an issue with `req.logout()`, ensure you’re using a version of Passport compatible with the session handling method used.

## License

This project is open-source and available under the MIT License.

--- 

This README provides all necessary information to understand, set up, and run GitHub OAuth authentication in this application.
