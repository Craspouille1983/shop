<template>
  <header>
    <headerNav />
    <carouselHeader />
  </header>
</template>

<script>
import './includes/css/index.min.css';
import headerNav from './components/header.vue';
import carouselHeader from './components/carouselHeader.vue';

export default {
  name: 'App',
  components: {
    headerNav,
    carouselHeader,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
}
</style>
