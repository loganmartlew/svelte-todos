<script lang="ts">
  export let removeCompletedTodos: () => void;
  export let clearTodos: () => void;
</script>

<div class="header">
  <h2>Todos</h2>
  <button class="link" on:click={removeCompletedTodos}>Remove Completed</button>
  <button class="link" on:click={clearTodos}>Clear List</button>
</div>

<style>
  .header {
    margin-bottom: 1em;
  }

  h2 {
    margin-top: 0;
    margin-bottom: 0.5em;
  }

  button.link {
    width: max-content;
    margin-bottom: 0.2em;
    padding: 0.5em 0.7em;
    background-color: rgb(39, 100, 255);
    border: none;
    border-radius: 0.5em;
    color: white;
  }
</style>
