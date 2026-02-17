
# 💻 Full-Stack e-Learning IDE

A web-based Integrated Development Environment (IDE) built with the MERN stack. This application serves as the coding sandbox module for a larger online educational platform, allowing users to write, execute, and securely save their code snippets.

## ✨ Features

* **Multi-Language Editor:** Integrated Monaco Editor (the core of VS Code) for professional syntax highlighting and code formatting.
* **Client-Side Execution:** Securely runs HTML/CSS/JS directly in the browser using sandboxed iframes.
* **Server-Side Architecture Setup:** UI and API routes structured to handle backend execution (Python, Java, C) via sandboxed environments.
* **User Authentication:** Secure JWT-based registration and login system, with passwords hashed via `bcryptjs`.
* **Database Integration:** Authenticated users can save their code snippets to a MongoDB database and retrieve them later.

## 🛠️ Tech Stack

* **Frontend:** React.js, Axios, `@monaco-editor/react`
* **Backend:** Node.js, Express.js
* **Database:** MongoDB, Mongoose
* **Authentication:** JSON Web Tokens (JWT)

## 🚀 Installation & Local Setup

### Prerequisites
* [Node.js](https://nodejs.org/) (v18 or higher)
* [MongoDB](https://www.mongodb.com/) installed and running locally on port `27017`.

### 1. Clone the Repository
\`\`\`bash
git clone https://github.com/Rajvardhan7030/web-IDE.git
cd web-IDE
\`\`\`

### 2. Backend Setup
Navigate to the backend directory and install dependencies:
\`\`\`bash
cd backend
npm install
\`\`\`
==============================================================================
==============================================================================
## Pro Tip: Don't Let Dependencies Play Hide-and-Seek 😈

Bro, you've probably heard the horror stories:  
"It works on my machine but fails in CI!"  
"Yesterday it ran fine, today random bug after npm install!"  

That's because `npm install` is a bit of a free spirit — it might grab a shiny new patch version (like lodash jumping from 4.17.21 to 4.17.22) if your `package.json` allows it with `^` or `~`. Cool for experimenting locally, but risky when you want **everyone** (your teammates, GitHub Actions, Docker, production) to run the **exact same versions** that were tested and working.

Enter `npm ci` — the strict aunty who follows the family recipe book (`package-lock.json`) to the letter:

- Wipes `node_modules` clean (no leftover junk)  
- Installs **precisely** what's locked in `package-lock.json` — no sneaky updates  
- Faster (skips all the version-matching drama)  
- Fails loudly if `package.json` and lockfile don't match (early warning!)  
- Zero surprises → reproducible builds, no "but it worked yesterday" excuses



================================================================================
================================================================================

Create a `.env` file in the `backend` directory with the following variables:
git push --set-upstream origin main
\`\`\`env
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/elearning-ide
JWT_SECRET=your_super_secret_key_here
\`\`\`

Start the backend server:
\`\`\`bash
npm run dev
\`\`\`

### 3. Frontend Setup
Open a new terminal, navigate to the frontend directory, and install dependencies:
\`\`\`bash
cd frontend
npm install
\`\`\`

Start the React development server:
\`\`\`bash
npm start
\`\`\`
The application will open automatically at `http://localhost:3000`.

## 🐛 Troubleshooting

* **Database Connection Failed:** Ensure your local MongoDB service is active. If you are on Linux, you may need to start the daemon (e.g., `sudo systemctl start mongodb`).
* **Port Conflicts:** If port 5000 or 3000 is already in use, find the lingering Node process and terminate it, or update the `PORT` in your `.env` file and frontend Axios requests.
* **500 Internal Server Error on Login/Register:** Verify that your `backend/.env` file exists, is in the correct directory, and contains a valid `JWT_SECRET`.
* **Code Execution Placeholder:** Server-side languages (Java, Python, C) are currently configured with a placeholder message to save local hardware resources. To enable them, integrate a Dockerized execution engine (like Piston) on your backend endpoint.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
