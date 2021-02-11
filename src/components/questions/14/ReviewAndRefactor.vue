<template>
  <!-- TODO: провести ревью компонента, и сделать рефакторинг -->
  <div>
    <TodoHeader :title="title" />
    <main>
      <div class="container">
        <TodoList v-if="todos.length">
          <TodoItem
            v-for="{ id, title, completed } in todos"
            :key="id"
            :title="title"
            :completed="completed"
          />
        </TodoList>
      </div>
    </main>
  </div>
</template>
<script>
/// тут могли бы быть скопед слоты
import TodoList from "@/components/questions/13/TodoList";
import TodoItem from "@/components/questions/13/TodoItem";
import TodoHeader from "@/components/questions/13/TodoHeader";

export default {
  components: {
    TodoItem,
    TodoHeader,
    TodoList,
  },
  name: "ReviewAndRefactor",
  data() {
    return {
      todos: [],
      title: "My todo list",
    };
  },
  created() {
    this.fetchTodos();
  },
  methods: {
    fetchTodos() {
      fetch("https://jsonplaceholder.typicode.com/todos/")
        .then((response) => response.json())
        .then((todos) => (this.todos = todos));
    },
  },
};
</script>
<style>
.container {
  padding: 1.5rem;
}
</style>
