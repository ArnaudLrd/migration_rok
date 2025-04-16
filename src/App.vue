<template>
  <div id="app">
    <MigrationForm />
  </div>
</template>

<script>
import MigrationForm from './components/MigrationForm.vue'

export default {
  name: 'App',
  components: {
    MigrationForm
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: #78350f;
}
</style>