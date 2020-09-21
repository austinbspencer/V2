<template>
  <div id="todo">
    <br />
    <h1>Todo List</h1>
    <br />
    <AddTodo v-on:add-todo="addTodo" />
    <todo-component></todo-component>
  </div>
</template>

<script>
import TodoComponent from "@/components/TodoComponent.vue";
import AddTodo from "@/components/AddTodo.vue";
import axios from "axios";

export default {
  components: {
    "todo-component": TodoComponent,
    AddTodo
  },
  methods: {
    addTodo(newTodo) {
      const { title, completed } = newTodo;
      axios
        .post("https://guldentech.com/austinapi/todos", {
          title,
          completed
        })
        .then(res => (this.todos = [...this.todos, res.data]))
        .catch(err => console.log(err));
      //... is spread operator to add on what's already in todos
      // this.todos = [...this.todos, newTodo]
    }
  }
};
</script>

<style></style>
