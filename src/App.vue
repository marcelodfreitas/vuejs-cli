<template>
  <div id="app">
    <UserComment />
  </div>
</template>

<script>
import UserComment from './components/UserComment.vue';

export default {
  name: 'App',
  components: {
    UserComment
  }
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  text-align: center;
  color: #333;
  margin: 20px;
}
</style>