<template>
  <nav
    class="
      grid grid-cols-2
      w-[100vw]
      items-center
      px-[8%]
      py-2
      lg:py-4
      bg-slate-100
    "
  >
    <div class="">
      <a class="">
        <h1 class="text-xl font-bold">Vue App</h1>
      </a>
    </div>
    <div class="flex justify-end">
      <Sidebar />
    </div>
  </nav>
</template>

<script setup>
import Sidebar from './components/Sidebar.vue';
</script>
