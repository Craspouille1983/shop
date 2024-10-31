<template>
  <header>
    <headerNav />
    <carouselHeader />
  </header>
  <main>
    <mainShop />
  </main>
</template>

<script>
import './includes/css/index.min.css';
import headerNav from './components/header.vue';
import carouselHeader from './components/carouselHeader.vue';
import mainShop from './components/main.vue';

export default {
  name: 'App',
  components: {
    headerNav,
    carouselHeader,
    mainShop,
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
main {
  padding: 3em 8rem;
}
</style>
