<script lang="ts">
  import type { Todo } from '../types/Todo';

  export let todo: Todo;
</script>

<div class="todo">
  <input type="checkbox" bind:checked={todo.complete} />
  <p class:checked={todo.complete}>{todo.text}</p>
</div>

<style>
  .todo {
    display: flex;
    align-items: center;
    gap: 0.5em;
    border-bottom: 1px solid rgb(170, 170, 170);
  }

  .checked {
    text-decoration: line-through;
  }
</style>
