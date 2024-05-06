<template>
  <div id="app" class="container-fluid purple-theme">
    <h1>Movie Management</h1>
    <MovieManagement />
  </div>
</template>

<script>
import MovieManagement from './components/MovieManagement.vue'

export default {
  name: 'App',
  components: {
    MovieManagement,
  },
}
</script>

<style>
.purple-theme {
  background-color: #8e24aa;
  color: white;
  padding: 20px;
}
</style>