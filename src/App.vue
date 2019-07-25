<template>
  <div id="app">
    <nav-bar />
    <router-view/>
  </div>
</template>

<script>
import NavBar from './components/Navbar.vue';

export default {
  components: {
    NavBar,
  },
};
</script>

<style>
body {
  font-family: Verdana, Geneva, sans-serif;
}
</style>
