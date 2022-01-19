<template>
  <div class="hello">
  <div id="app">
  <h1>Posts</h1>
  <div v-for="item in posts" :key="item.id">
    {{item.title}}
  </div>
</div>
  </div>
</template>

<script>
import {ref} from "vue";
import axios from "axios";
export default {
async setup() {
    const posts = ref(null);
    const response = await axios.get("https://jsonplaceholder.typicode.com/posts")
    .then(response => posts.value = response.data)
  return {
      posts,
      response
  }
}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
