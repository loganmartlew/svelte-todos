<main class="container">
  <h1>Todos in Svelte</h1>
  <form on:submit|preventDefault={() => {}}>
    <div class="form-control">
      <label for="todo">Todo</label>
      <input type="text" name="todo" id="todo" />
    </div>
    <button type="submit">Add Todo</button>
  </form>
</main>

<style>
  .container {
    max-width: 500px;
    margin: 0 auto;
    padding: 0 1rem;
  }

  form {
    display: flex;
    flex-direction: column;
    gap: 0.7em;
    padding: 1.5em;
    background-color: rgb(243, 243, 243);
    border: 3px solid rgb(135, 135, 135);
    border-radius: 1em;
  }

  form .form-control {
    display: flex;
    flex-direction: column;
    gap: 0.2em;
  }

  form input {
    padding: 0.5em 0.7em;
    border: 3px solid rgb(174, 174, 174);
    border-radius: 0.5em;
  }

  form input:focus {
    outline: none;
    border-color: rgb(39, 100, 255);
  }

  form button {
    width: max-content;
    padding: 0.5em 0.7em;
    background-color: rgb(39, 100, 255);
    border: none;
    border-radius: 0.5em;
    color: white;
  }
</style>
