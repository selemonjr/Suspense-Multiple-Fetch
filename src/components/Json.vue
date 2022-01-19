<template>
  <div class="hello">
    <div id="app">
  <h1>Users</h1>
  <div v-for="item in data" :key="item.id">
    {{item.name}}
  </div>
</div>
  </div>
</template>

<script>
import {ref} from "vue";
import axios from "axios";
export default {
async setup() {
  const data = ref(null);
  const fetch = await axios.get("https://jsonplaceholder.typicode.com/users")
  .then(fetch => data.value = fetch.data)
  return {
    data,
    fetch
  }
}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
