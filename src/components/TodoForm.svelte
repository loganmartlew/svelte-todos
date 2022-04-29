<script lang="ts">
  import Card from '../components/Card.svelte';

  export let handleNewTodo: (text: string) => void;

  let text: string = '';

  const onSubmit = () => {
    handleNewTodo(text);
  };
</script>

<Card>
  <form on:submit|preventDefault={onSubmit}>
    <div class="form-control">
      <label for="todo">Todo</label>
      <input type="text" name="todo" id="todo" bind:value={text} />
    </div>
    <button type="submit">Add Todo</button>
  </form>
</Card>

<style>
  form {
    display: flex;
    flex-direction: column;
    gap: 0.7em;
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
