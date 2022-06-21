<template>
  <div class="lg:hidden">
    <button
      type="button"
      @click="openSidebar"
      class="
        rounded-md
        bg-transparent
        px-4
        py-2
        text-2xl
        font-medium
        text-black/90
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
        enter="duration-400 ease-in-out transition"
        enter-from="opacity-0"
        enter-to="opacity-100"
        leave="duration-400 ease-in"
        leave-from="opacity-100"
        leave-to="opacity-0"
      >
        <div class="fixed inset-0 bg-black bg-opacity-40" />
      </TransitionChild>

      <div class="fixed inset-0 overflow-y-auto">
        <div class="flex min-h-full items-center justify-center text-center">
          <TransitionChild
            as="template"
            enter="transition ease-in duration-[.8s] transform"
            enter-from="translate-x-full "
            leave="transition ease-in duration-[.5s] transform"
            leave-from="translate-x-0"
            leave-to="-translate-x-full"
          >
            <DialogPanel
              class="
                w-full
                -translate
                overflow-hidden
                bg-white
                px-6
                text-left
                align-middle
                shadow-xl
                transition-all
                top-0
                left-0
                absolute
                h-[100vh]
                md:w-[450px]
              "
            >
              <div class="mt-2 flex justify-end">
                <button
                  type="button"
                  class="
                    inline-flex
                    justify-center
                    rounded-md
                    border border-transparent
                    px-4
                    py-2
                    text-3xl
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
              <DialogTitle
                as="h2"
                class="text-3xl font-black leading-6 text-gray-900 text-center"
              >
                Menu
              </DialogTitle>
              <div class="mt-2 flex flex-col items-center h-full mt-60">
                <a
                  class="mb-4 text-black/90 font-bold text-2xl uppercase"
                  href="/"
                  >Home</a
                >
                <a
                  class="mb-4 text-black/90 font-bold text-2xl uppercase"
                  href="/about"
                  >About</a
                >
                <a
                  class="mb-4 text-black/90 font-bold text-2xl uppercase"
                  href="/contact"
                  >Contact</a
                >
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
