<template>
  <div id="todo">
    <br />
    <br />
    <AddTodo v-on:add-todo="addTodo" />
    <br />
    <TodoComponent v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import TodoComponent from "@/components/TodoComponent";
import AddTodo from "@/components/AddTodo";
import axios from "axios";

export default {
  name: "Todo",
  components: {
    TodoComponent,
    AddTodo
  },
  data() {
    return {
      todos: []
    };
  },
  methods: {
    deleteTodo(Title, Completed, id) {
      axios
        .post(`https://guldentech.com/austinapi/todos/rm`, {
          Title,
          Completed,
          id
        })
        .then(
          res =>
            (this.todos = this.todos.filter(todo => todo.id !== id, res.data))
        )
        .catch(err => console.log(err));
      // this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo) {
      const { Title, Completed } = newTodo;

      axios
        .post("https://guldentech.com/austinapi/todos", {
          Title,
          Completed
        })
        .then(res => (this.todos = [...this.todos, res.data]))
        .catch(err => console.log(err));
      //... is spread operator to add on what's already in todos
      // this.todos = [...this.todos, newTodo]
    }
  },
  created() {
    axios
      .get("https://guldentech.com/austinapi/todos")
      .then(res => (this.todos = res.data))
      .catch(err => console.log(err));
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #666;
}
</style>
