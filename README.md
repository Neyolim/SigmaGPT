# SigmaGPT
[![Ask DeepWiki](https://devin.ai/assets/askdeepwiki.png)](https://deepwiki.com/Neyolim/SigmaGPT)

SigmaGPT is a full-stack chat application that leverages the Google Gemini API to provide an interactive, AI-powered conversational experience. It features a React-based frontend and a Node.js/Express backend with MongoDB for data persistence.

## Features

*   **AI-Powered Conversations**: Engage in dynamic conversations with the Google Gemini model.
*   **Chat History**: All chat threads are saved to a MongoDB database, allowing you to revisit past conversations.
*   **Thread Management**: Create new chats, switch between conversation threads, and delete threads you no longer need.
*   **Real-time Response Streaming**: AI responses are displayed with a word-by-word typing effect for a more engaging user experience.
*   **Syntax Highlighting**: Code blocks within the AI's responses are automatically highlighted for readability.

## Tech Stack

*   **Frontend**: React, Vite, React Markdown, React Spinners, CSS
*   **Backend**: Node.js, Express.js, Mongoose
*   **Database**: MongoDB
*   **AI**: Google Gemini API

## Project Structure

The repository is organized into two main directories:

*   `Frontend/`: Contains the React front-end application built with Vite.
    *   `src/components`: Reusable React components for the UI (Sidebar, Chat Window, etc.).
    *   `src/App.jsx`: Main application component managing global state.
    *   `src/MyContext.jsx`: React Context for state management across components.
*   `Backend/`: Contains the Node.js server.
    *   `server.js`: The main entry point for the Express server.
    *   `routes/`: API route definitions for chat and thread management.
    *   `models/`: Mongoose schemas for the database.
    *   `utils/gemini.js`: A utility function to interact with the Google Gemini API.

## API Endpoints

The backend server exposes the following RESTful API endpoints:

| Method | Endpoint                 | Description                                     |
|--------|--------------------------|-------------------------------------------------|
| `POST` | `/api/chat`              | Sends a user message to the AI and gets a reply. Creates or updates a chat thread. |
| `GET`  | `/api/thread`            | Fetches all saved chat threads, sorted by the most recently updated. |
| `GET`  | `/api/thread/:threadId`  | Fetches all messages within a specific thread.  |
| `DELETE`| `/api/thread/:threadId` | Deletes a specific chat thread from the database. |

## Local Setup and Installation

Follow these steps to run the project on your local machine.

### Prerequisites

*   Node.js and npm (or a compatible package manager)
*   Access to a MongoDB database instance
*   A Google Gemini API Key

### 1. Clone the Repository

```sh
git clone https://github.com/neyolim/sigmagpt.git
cd sigmagpt
```

### 2. Backend Setup

1.  Navigate to the `Backend` directory:
    ```sh
    cd Backend
    ```

2.  Install the required dependencies:
    ```sh
    npm install
    ```

3.  Create a `.env` file in the `Backend` directory and add your environment variables:
    ```env
    # Your MongoDB connection string
    CONNECTION_STRING=mongodb+srv://<user>:<password>@<cluster-url>/<database-name>

    # Your Google Gemini API key
    GOOGLE_API_KEY=YOUR_GOOGLE_API_KEY
    ```

4.  Start the backend server:
    ```sh
    npm start
    ```
    The server will be running on `http://localhost:8080`.

### 3. Frontend Setup

1.  Open a new terminal and navigate to the `Frontend` directory:
    ```sh
    cd Frontend
    ```

2.  Install the required dependencies:
    ```sh
    npm install
    ```

3.  Start the Vite development server:
    ```sh
    npm run dev
    ```
    The application will be available at `http://localhost:5173` (or another port if 5173 is in use).
