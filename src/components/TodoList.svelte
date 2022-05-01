<script lang="ts">
  import Card from './Card.svelte';
  import TodoListHeader from './TodoListHeader.svelte';
  import TodoItem from './TodoItem.svelte';
  import type { Todo } from '../types/Todo';

  export let todos: Todo[];
  export let handleDeleteTodo: (id: string) => void;
  export let removeCompletedTodos: () => void;
  export let clearTodos: () => void;
</script>

<Card>
  {#if todos.length === 0}
    <p>No todos yet.</p>
  {:else}
    <TodoListHeader {removeCompletedTodos} {clearTodos} />
    <div class="todos">
      {#each todos as todo}
        <TodoItem {todo} {handleDeleteTodo} />
      {/each}
    </div>
  {/if}
</Card>

<style>
  .todos {
    border-top: 1px solid rgb(170, 170, 170);
  }
</style>
