<template>
  <nav class="grid grid-cols-2 w-[100vw] items-center px-[8%] py-2 lg:py-4">
    <div class="">
      <a class="">
        <h1 class="text-xl font-bold">Vue App</h1>
      </a>
    </div>
    <div class="flex lg:hidden justify-end">
      <Sidebar />
    </div>
    <div class="hidden lg:flex justify-end">
      <a class="uppercase mr-8" href="/">Home</a>
      <a class="uppercase mr-8" href="/about">About</a>
      <a class="uppercase " href="/contact">Contact</a>
    </div>
  </nav>
</template>

<script setup>
import Sidebar from './components/Sidebar.vue';
</script>
