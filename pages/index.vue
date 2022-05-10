<template>
  <main class="h-screen w-screen flex items-center justify-center">
    <button class="btn" @click="toggleDialog">Open Dialog</button>
    <ui-dialog
      :show="showDialog"
      class="fixed top-10 left-1/2 transform -translate-x-1/2"
    >
      <article class="space-y-4">
        <h1 class="text-xl font-bold">I am the dialog</h1>
        <input
          class="border-gray-400 border placeholder-gray-400 rounded px-3 py-2 w-full"
          placeholder="I am an input"
        />
        <button class="btn" @click="toggleDialog">Close Dialog</button>
      </article>
    </ui-dialog>
  </main>
</template>

<script>
import { ref } from "@nuxtjs/composition-api";
export default {
  name: "IndexPage",
  setup() {
    const showDialog = ref(false);

    function toggleDialog() {
      showDialog.value = !showDialog.value;
    }

    return { showDialog, toggleDialog };
  },
};
</script>

<style>
.btn {
  @apply bg-blue-600 text-white font-semibold rounded px-3 py-2;
}

.btn:focus {
  @apply outline-none ring-2 ring-offset-1 ring-blue-600;
}
</style>
