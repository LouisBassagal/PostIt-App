<template>
  <PostIt/>
</template>

<script>
import PostIt from './components/PostIt.vue'

export default {
  name: 'MainPage',
  components: {
    PostIt
  },
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
body {
  background-color: lightgrey;
}
.PostIt {
  grid-auto-rows: auto;
  grid-auto-columns: auto;
}
</style>
