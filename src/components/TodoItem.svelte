<script lang="ts">
  import MdDelete from 'svelte-icons/md/MdDelete.svelte';
  import type { Todo } from '../types/Todo';

  export let todo: Todo;
  export let handleDeleteTodo: (id: string) => void;
</script>

<div class="todo">
  <input type="checkbox" bind:checked={todo.complete} />
  <p class:strike={todo.complete}>{todo.text}</p>
  <button on:click={() => handleDeleteTodo(todo.id)}>
    <MdDelete />
  </button>
</div>

<style>
  .todo {
    display: flex;
    align-items: center;
    gap: 0.5em;
    border-bottom: 1px solid rgb(170, 170, 170);
  }

  .todo p {
    flex-grow: 1;
  }

  .todo button {
    height: 27px;
    background: none;
    border: none;
    color: rgb(255, 0, 64);
    cursor: pointer;
  }

  .todo button:hover {
    color: rgb(255, 66, 98);
  }

  .strike {
    text-decoration: line-through;
  }
</style>
