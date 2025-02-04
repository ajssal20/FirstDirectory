<script>
    import { writable } from "svelte/store";
  
    let inputText = writable("");
    let displayText = writable("Willkommen auf meiner Seite!");
  
    function updateText() {
      displayText.set($inputText);
    }
  </script>
  
  <div>
    <h1>{$displayText}</h1>
    <h2>Gib einen neuen Text ein:</h2>
  
    <input type="text" bind:value={$inputText} placeholder="Neuer Text hier..." />
    <button on:click={updateText}>Text ändern</button>
  </div>
  