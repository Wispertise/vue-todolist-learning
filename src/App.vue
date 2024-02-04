<template>
<noteForm></noteForm>
</template>

<script>
import noteForm from "./components/noteForm.vue";
export default {
  name: 'App',
  components: {
    noteForm,
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
