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
