<template>
  <nav class="grid grid-cols-2 w-[100vw] items-center px-[8%] py-2 lg:py-4">
    <div class="">
      <a class="">
        <h1 class="text-xl font-bold">Vue App</h1>
      </a>
    </div>

    <Sidebar />

    <div class="hidden">
      <a class="uppercase mr-8" href="/">Home</a>
      <a class="uppercase mr-8" href="/about">About</a>
      <a class="uppercase" href="/contact">Contact</a>
    </div>
  </nav>
</template>

<script>
import Sidebar from './Sidebar.vue';
import { ref } from 'vue';

import {
  TransitionRoot,
  TransitionChild,
  Dialog,
  DialogPanel,
  DialogTitle,
} from '@headlessui/vue';

const isOpen = ref(false);

function closeSidebar() {
  isOpen.value = false;
}
function openSidebar() {
  isOpen.value = true;
}
</script>
