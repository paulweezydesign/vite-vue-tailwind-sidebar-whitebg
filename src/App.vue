<script>
import Home from './views/Home.vue';
import About from './views/About.vue';
import Kittens from './views/Kittens.vue';
import Contact from './views/Contact.vue';
import NotFound from './views/NotFound.vue';

const routes = {
  '/': Home,
  '/about': About,
  '/kittens': Kittens,
  '/contact': Contact,
};

export default {
  data() {
    return {
      currentPath: window.location.hash,
    };
  },
  computed: {
    currentView() {
      return routes[this.currentPath.slice(1) || '/'] || NotFound;
    },
  },
  mounted() {
    window.addEventListener('hashchange', () => {
      this.currentPath = window.location.hash;
    });
  },
};
</script>

<template>
  <nav class="">
    <a href="#/">Home</a> | <a href="#/about">About</a> |
    <a href="#/kittens">Kittens</a> | <a href="#/contact">Contact</a> |
  </nav>
  <component :is="currentView" />
</template>
