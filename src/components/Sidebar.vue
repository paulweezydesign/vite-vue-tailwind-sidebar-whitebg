<template>
  <div class="fixed inset-0">
    <button
      type="button"
      @click="openSidebar"
      class="
        rounded-md
        bg-black bg-opacity-20
        px-4
        py-2
        text-sm
        font-medium
        text-white
        hover:bg-opacity-30
        focus:outline-none
        focus-visible:ring-2
        focus-visible:ring-white
        focus-visible:ring-opacity-75
      "
    >
      <i class="fa fa-bars" />
    </button>
  </div>
  <TransitionRoot appear :show="isOpen" as="template">
    <Dialog as="div" @close="closeSidebar" class="relative z-10">
      <TransitionChild
        as="template"
        enter="duration-300 ease-out"
        enter-from="opacity-0"
        enter-to="opacity-100"
        leave="duration-200 ease-in"
        leave-from="opacity-100"
        leave-to="opacity-0"
      >
        <div class="fixed inset-0 bg-black bg-opacity-25" />
      </TransitionChild>

      <div class="fixed inset-0 overflow-y-auto">
        <div
          class="flex min-h-full items-center justify-center p-4 text-center"
        >
          <TransitionChild
            as="template"
            enter="duration-300 ease-out"
            enter-from="opacity-0 scale-95"
            enter-to="opacity-100 scale-100"
            leave="duration-200 ease-in"
            leave-from="opacity-100 scale-100"
            leave-to="opacity-0 scale-95"
          >
            <DialogPanel
              class="
                max-w-md
                transform
                overflow-hidden
                bg-white
                p-6
                text-left
                align-middle
                shadow-xl
                transition-all
                top-0
                right-0
                absolute
                h-[100vh]
                w-[450px]
              "
            >
              <DialogTitle
                as="h2"
                class="text-2xl font-black leading-6 text-gray-900 text-center"
              >
                Menu
              </DialogTitle>

              <div class="mt-4">
                <button
                  type="button"
                  class="
                    inline-flex
                    justify-center
                    rounded-md
                    text-3xl
                    border border-transparent
                    px-4
                    py-2
                    text-sm
                    font-medium
                    text-blue-900
                    focus:outline-none
                    focus-visible:ring-2
                    focus-visible:ring-blue-500
                    focus-visible:ring-offset-2
                  "
                  @click="closeSidebar"
                >
                  <i class="fa fa-times" />
                </button>
              </div>

              <div class="mt-2 flex flex-col">
                <a href="/">Home</a>
                <a href="/about">About</a>
                <a href="/contact">Contact</a>
              </div>
            </DialogPanel>
          </TransitionChild>
        </div>
      </div>
    </Dialog>
  </TransitionRoot>
</template>

<script setup>
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
