<template>
  <Suspense>
    <template #default>
      <div>
        <Json/>
        <Fetcher/>
      </div>
    </template>
    <template #fallback>
      <div>
        <h2>Loading Users and Posts.....</h2>
      </div>
    </template>
  </Suspense>
</template>

<script>
import Json from './components/Json.vue'
import Fetcher from "./components/Fetcher.vue"
export default {
  name: 'App',
  components: {
    Json,
    Fetcher
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
