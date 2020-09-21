<template>
  <div id="todo">
    <h1>API Access</h1>
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
