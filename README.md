# mad-tasker
BMAD experiment
# Project Overview

This project is a Twitch extension that displays tasks from a Notion database as a video overlay on a livestream. Viewers can see the streamer's current tasks and submit their own tasks for approval. The extension consists of three frontend components (`code.html`, `panel.html`, and `config.html`) and a backend service (`ebs.js`).

## Technologies Used

-   **Frontend:** HTML, CSS, JavaScript, Tailwind CSS
-   **Backend:** Node.js, Express.js
-   **Database:** Notion
-   **Authentication:** Twitch Extension JWTs

## Architecture

The project follows a client-server architecture:

-   **Frontend:** The frontend consists of three static HTML files that are served to the user's browser. These files communicate with the backend EBS to fetch data and perform actions.
-   **Backend (EBS):** The backend is a Node.js server that acts as an Extension Backend Service (EBS). It connects to the Notion API to manage tasks and exposes a REST API for the frontend to consume. The EBS is responsible for authenticating requests from the frontend using Twitch Extension JWTs.

# Building and Running

## Prerequisites

-   Node.js and npm
-   A Twitch account with Extension developer access
-   A Notion account and API key

## Installation

1.  **Install dependencies:**
    ```bash
    npm install
    ```

## Running the Application

Local development requires running three separate servers in different terminal sessions.

1.  **Terminal 1: Start the Mock EBS**
    This server simulates the Twitch backend and provides mock data for UI development.
    ```bash
    node mock-ebs.js
    ```

2.  **Terminal 2: Start the Notion EBS (Main Backend)**
    This is the primary backend service that connects to the Notion API.
    ```bash
    npm run start:ebs
    ```

3.  **Terminal 3: Start the Frontend Server**
    This server hosts the static HTML and CSS files.
    ```bash
    npx http-server -p 8080
    ```

# Development Conventions

## Coding Style

The project uses [Prettier](https://prettier.io/) for code formatting. It is recommended to use a Prettier extension in your code editor to automatically format code on save.

## Testing

There are no automated tests in this project. All testing is done manually. For detailed instructions on how to test the extension locally, see the `LOCAL_TESTING.md` file.

## Contribution Guidelines

There are no explicit contribution guidelines in this project. However, it is recommended to follow the existing coding style and to create a pull request for any changes.
