# Svelte Project

A simple Svelte project with dynamic content updates and styled components.

## Creating a Project

If you're seeing this, you've probably already done this step. Congrats!

```bash
# create a new project in the current directory
npx degit sveltejs/template my-svelte-app

# navigate into the project folder
cd my-svelte-app

# install dependencies
npm install
```

## Developing

Once you've installed the dependencies, start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Project Structure

This project contains the following main files:

### `App.svelte`

```svelte
<script>  
  // Imports the CSS file for global styling
  import "../app.css"; 
</script>

<header>
  <!-- Website heading -->
  <h1>My Svelte Page</h1>
</header>

<main>
  <!-- Slot for dynamic content inserted by a parent component -->
  <slot />
</main>

<footer>
  <!-- Footer with a welcome message -->
  <p>My first Svelte website, you are welcome and have lots of fun!!!!!!</p>
</footer>
```

### `TextUpdater.svelte`

```svelte
<script>
  // Import "writable" from Svelte to create reactive variables (stores)
  import { writable } from "svelte/store";

  // Creates a writable store for user input
  let inputText = writable("");

  // Creates a store for the displayed text with a default value
  let displayText = writable("Welcome to my page!");

  // Function to update the displayed text with the current input text
  function updateText() {
      displayText.set($inputText); // $inputText retrieves the current value of the store
  }
</script>

<div>
  <!-- Displays the current text from the store -->
  <h1>{$displayText}</h1>

  <h2>Enter a new text:</h2>

  <!-- Input field bound to inputText for two-way data binding -->
  <input type="text" bind:value={$inputText} placeholder="Enter new text here..." />

  <!-- Button that calls the updateText function when clicked -->
  <button on:click={updateText}>Change Text</button>
</div>
```

### `app.css`

```css
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  text-align: center;
  background: #ffe4ec; /* Soft pink background */
  color: #880e4f; /* Dark pink text color */
}

header, footer {
  background: #ff4f8b; /* Vibrant pink */
  color: white;
  padding: 1rem;
}

main {
  padding: 2rem;
}

h1 {
  color: #c2185b; /* Medium pink */
}

input {
  margin-top: 1rem;
  padding: 0.5rem;
  font-size: 1rem;
  border: 1px solid #ff4f8b;
  border-radius: 5px;
  outline: none;
}

button {
  margin-top: 1rem;
  padding: 0.5rem 1rem;
  font-size: 1rem;
  background: #ff4f8b; /* Button background color */
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer; /* Changes cursor to pointer on hover */
}

button:hover {
  background: #d81b60; /* Darker pink when hovering */
}

footer {
  margin-top: 2rem;
  font-size: 0.9rem;
}
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with:

```bash
npm run preview
```

> To deploy your app, you may need to install an [adapter](https://svelte.dev/docs/kit/adapters) for your target environment.
