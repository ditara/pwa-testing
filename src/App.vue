<template>
  <div>
    <navbar/>
    <b-container fluid>
      <category/>
    </b-container>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import Category from './components/Category.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    Category,
  },
};
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
} */
.container-fluid {
  width: 100%;
  justify-content: center;
  align-items: center;
  text-align: none;
}
</style>
