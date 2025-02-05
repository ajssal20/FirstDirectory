# My Svelte Project

A simple Svelte project with dynamic content updates and styled components.

## Description

This project showcases the fundamental features of Svelte, including reactive programming and dynamic content updates. Users can input text, and the application will display it in real-time, providing an interactive and engaging user experience. The project utilizes Svelte's powerful reactive features, making it easy to build modern web applications with minimal boilerplate code.

## Getting Started

Follow the steps below to set up and run the project locally on your machine. This guide assumes you have Node.js and npm (Node Package Manager) installed. If you haven't installed them yet, please visit the [Node.js website](https://nodejs.org/) to download and install the latest version.

### Creating a Project

If you're seeing this, you've probably already done this step. Congrats! If not, here's how to get started:

1. **Create a new project in the current directory**: Use the command below to scaffold a new Svelte project using the official template. This command utilizes `degit`, which allows you to clone a GitHub repository without including its history, resulting in a clean project setup.

    ```bash
    npx degit sveltejs/template my-svelte-app
    ```

2. **Navigate into the project folder**: Change your directory to the newly created project folder. This is where all your project files will be located.

    ```bash
    cd my-svelte-app
    ```

3. **Install dependencies**: Once you're inside the project folder, run the following command to install all necessary dependencies specified in the `package.json` file. This will download and set up the libraries required to run your Svelte application.

    ```bash
    npm install
    ```

    During this process, npm will fetch all packages required for the project, allowing you to use features like Svelte's reactive components and other libraries that may be included in the project.

4. **Start the development server**: After the installation is complete, you can start the local development server to see your application in action. The following command will start the server and you can view your app in the browser.

    ```bash
    npm run dev
    ```

5. **Open the app in your browser**: By default, the development server runs on `localhost:5000`. You can open your web browser and navigate to `http://localhost:5000` to see your application. If you want the server to automatically open a new tab in your default web browser, you can use the following command:

    ```bash
    npm run dev -- --open
    ```

This command will compile your Svelte project and open it directly in your browser for you to view and interact with.

### Project Structure

This project contains the following main files:

- **`App.svelte`**: The main application component that serves as the entry point for your Svelte app.
- **`TextUpdater.svelte`**: A component that allows users to input text and see it updated in real-time.
- **`app.css`**: The stylesheet for global styling applied throughout the application.

## Building

To create a production version of your app, which optimizes your code for deployment, run the following command:

```bash
npm run build
