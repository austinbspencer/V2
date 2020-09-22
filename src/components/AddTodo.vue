<template>
  <div>
    <form @submit="addTodo">
      <input
        type="text"
        v-model="Title"
        name="Title"
        placeholder="Add Todo..."
      />
      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>

<script>
// import uuid from "uuid";
export default {
  name: "AddTodo",
  data() {
    return {
      Title: ""
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        // no longer need this since our API gives an automatic ID
        // id: uuid.v4(),
        Title: this.Title,
        Completed: false
      };
      // Send to parent
      this.$emit("add-todo", newTodo);

      // clear title
    //   this.Title = "";
    }
  }
};
</script>

<style scoped>
form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 5px;
}

input[type="submit"] {
  flex: 2;
}
</style>
