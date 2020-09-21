<template>
  <div id="todo"></div>
</template>

<script>
import axios from "axios";

export default {
  name: "app",
  data() {},
  async created() {
    try {
      const res = await axios.get("https://jsonplaceholder.typicode.com/posts");
      console.log(res);
      console.log(res.data);
    } catch (e) {
      console.error(e);
    }
  }
};
</script>

<style></style>
