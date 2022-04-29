<script lang="ts">
  import Container from '../components/Container.svelte';
  import TodoForm from '../components/TodoForm.svelte';

  interface Todo {
    text: string;
    complete: boolean;
  }

  let todos: Todo[] = [];

  const addTodo = (text: string) => {
    const newTodo = {
      text,
      complete: false
    };
  };
</script>

<Container>
  <h1>Todos in Svelte</h1>
  <TodoForm handleNewTodo={addTodo} />
</Container>
