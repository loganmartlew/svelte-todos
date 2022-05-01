<script lang="ts">
  import { v4 as uuid } from 'uuid';
  import Container from '../components/Container.svelte';
  import TodoForm from '../components/TodoForm.svelte';
  import TodoList from '../components/TodoList.svelte';
  import type { Todo } from '../types/Todo';

  let todos: Todo[] = [];

  const addTodo = (text: string) => {
    console.log(text);
    const newTodo = {
      id: uuid(),
      text,
      complete: false
    };

    todos = [...todos, newTodo];
  };
</script>

<Container>
  <h1>Todos in Svelte</h1>
  <TodoForm handleNewTodo={addTodo} />
  <TodoList {todos} />
</Container>
