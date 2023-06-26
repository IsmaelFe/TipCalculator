<script>
  import { createEventDispatcher } from "svelte";
  export let custom;

  const dispatch = createEventDispatcher();

  function pressed(value) {
    dispatch("pressed", value);
  }
</script>

<div>
  <button
    on:click={() => {
      pressed(5);
    }}>5%</button
  >
  <button
    on:click={() => {
      pressed(10);
    }}>10%</button
  >
  <button
    on:click={() => {
      pressed(15);
    }}>15%</button
  >
  <button
    on:click={() => {
      pressed(25);
    }}>25%</button
  >
  <button
    on:click={() => {
      pressed(50);
    }}>50%</button
  >
  <input
    type="text"
    placeholder="Custom"
    bind:value={custom}
    on:input={() => pressed(custom)}
  />
</div>

<style scoped>
  div {
    display: grid;
    grid-template-columns: repeat(3, 30%);
    gap: 12px;
  }

  button {
    font-family: "Space Mono", monospace;
    font-weight: 500;
    font-size: 1em;
    color: white;
    background-color: #01464d;
    border: none;
    border-radius: 3px;
    padding: 6px 12px;
  }

  button:hover {
    cursor: pointer;
    background-color: #9fe9de;
    color: #01464d;
  }

  input {
    color: #547876;
    font-weight: 600;
    background-color: #f3f8fb;
    border: none;
    border-radius: 3px;
    padding: 10px;
    text-align: center;
    font-family: "Space Mono", monospace;
  }

  input:hover {
    cursor: pointer;
  }

  input::placeholder {
    color: #587472;
  }

  input:focus {
    outline: 2px solid #58aa9c;
  }
</style>
