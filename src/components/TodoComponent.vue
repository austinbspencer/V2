<template>
  <div id="todo">
    <b-card v-if="posts && posts.length">
      <b-card-text v-for="(obj, key) in posts" :key="key">
        <p>
          <strong>{{ obj.title }}</strong>
        </p>
        <p>{{ obj.completed }}</p>
      </b-card-text>
    </b-card>

    <ul v-if="errors && errors.length">
      <template v-for="error of errors">
        {{ error.message }}
      </template>
    </ul>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      posts: []
    };
  },

  // Fetches posts when the component is created.
  created() {
    axios
      .get("https://guldentech.com/austinapi/todos")
      .then(res => (this.posts = res.data))
      .catch(err => console.log(err));

    // async / await version (created() becomes async created())
    //
    // try {
    //   const response = await axios.get(`http://jsonplaceholder.typicode.com/posts`)
    //   this.posts = response.data
    // } catch (e) {
    //   this.errors.push(e)
    // }
  }
};
</script>

<style></style>
