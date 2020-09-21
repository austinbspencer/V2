<template>
  <div id="todo">
    <b-row class="submit-item">
      <b-col sm="2"></b-col>
      <b-col sm="8">
        <form>
          <input type="text" name="title" placeholder="Add Todo..." />
          <input type="submit" value="Submit" class="btn" />
        </form>
      </b-col>
      <b-col sm="2"></b-col>
    </b-row>
    <br />
    <br />
    <b-row class="todo-item" v-for="(obj, key) in posts" :key="key">
      <b-col sm="2">
        <template>
          <b-form-checkbox
            id="checkbox-1"
            :name="obj.Title"
            :checked="obj.Completed"
          >
          </b-form-checkbox>
        </template>
      </b-col>
      <b-col sm="8">
        <p v-if="obj.Completed == 'false'" class="float-left">
          <strong> {{ obj.Title }} </strong>
        </p>
        <p v-else class="float-left">
          <strong>
            <strike> {{ obj.Title }} </strike>
          </strong>
        </p>
      </b-col>
      <b-col sm="2">
        <button class="del">x</button>
      </b-col>
      <hr />
    </b-row>
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

<style>
input[type="text"] {
  flex: 10;
  padding: 5px;
}

.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #ccc dotted;
}
.del {
  background: #ff0000;
  color: #fff;
  border: none;
  padding: 5px 9px;
  /* border-radius: 50%; */
  cursor: pointer;
  /* float: right; */
}
.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  margin-left: 10px;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #666;
}
</style>
