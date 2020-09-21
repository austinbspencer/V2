<template>
  <div id="todo">
    <br />
    <h1>Todo List</h1>
    <br />
    <todo-component></todo-component>
  </div>
</template>

<script>
import TodoComponent from "@/components/TodoComponent.vue";

export default {
  components: {
    "todo-component": TodoComponent
  }
};
</script>

<style></style>
