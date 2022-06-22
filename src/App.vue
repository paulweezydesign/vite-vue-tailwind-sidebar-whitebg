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
  <nav class="grid grid-cols-2 items-center px-[8%] py-4 w-[100vw]">
    <div class="text-xl font-black text-black/90 uppercase">
      My Cute Kittens
    </div>
    <div class="flex justify-end">
      <a class="uppercase mr-8 text-black/90 font-bold" href="#/">Home</a> |
      <a class="uppercase mr-8 text-black/90 font-bold" href="#/about">About</a>
      |
      <a class="uppercase mr-8 text-black/90 font-bold" href="#/kittens"
        >Kittens</a
      >
      |
      <a class="uppercase text-black/90 font-bold" href="#/contact">Contact</a>
      |
    </div>
  </nav>
  <component class="text-black/90" :is="currentView" />
</template>
