
<template>
  <div id="app">
    <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo" />
    <AddTodo v-on:add-todo="addTodo" />
    <h2>Feel free to fork the following repo and create a PR to contribute:</h2>
    <br />
    <a
      href="https://github.com/michael-spengler/p2p-tasks"
      target="_blank"
      rel="noopener noreferrer"
    >https://github.com/michael-spengler/p2p-tasks</a>
  </div>
</template>

<script>
import Todos from "./components/Todos.vue";
import AddTodo from "./components/AddTodo";

export default {
  name: "app",

  components: {
    Todos,
    AddTodo
  },

  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Go workout",
          completed: false
        },
        {
          id: 2,
          title: "Do laundry",
          completed: false
        },
        {
          id: 3,
          title: "Cook food",
          completed: false
        },
        {
          id: 4,
          title: "Clean up room",
          completed: false
        },
        {
          i: 5,
          title: "Finish work",
          completed: false
        }
      ]
    };
  },

  methods: {
    addTodo(newTodoObj) {
      this.todos = [...this.todos, newTodoObj];
    },
    deleteTodo(todoId) {
      this.todos = this.todos.filter(todo => todo.id !== todoId);
    }
  }
};
</script>
<style>
</style>