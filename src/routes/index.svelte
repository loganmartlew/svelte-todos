<script lang="ts">
  import { v4 as uuid } from 'uuid';
  import Container from '../components/Container.svelte';
  import TodoForm from '../components/TodoForm.svelte';
  import TodoList from '../components/TodoList.svelte';
  import type { Todo } from '../types/Todo';

  let todos: Todo[] = [];

  const addTodo = (text: string) => {
    const newTodo = {
      id: uuid(),
      text,
      complete: false
    };

    todos = [...todos, newTodo];
  };

  const deleteTodo = (id: string) => {
    const newTodos = todos.filter((todo) => todo.id !== id);

    todos = newTodos;
  };
</script>

<Container>
  <h1>Todos in Svelte</h1>
  <TodoForm handleNewTodo={addTodo} />
  <TodoList {todos} handleDeleteTodo={deleteTodo} />
</Container>
