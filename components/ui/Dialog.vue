<template>
  <transition name="slide-fade" appear>
    <div v-show="show" class="rounded border border-gray-400 bg-white p-3">
      <slot></slot>
    </div>
  </transition>
</template>

<script>
export default {
  name: "UiDialog",
  props: {
    show: Boolean,
  },
};
</script>

<style>
.slide-fade-enter,
.slide-fade-leave-to {
  @apply scale-90 opacity-0;
}

.slide-fade-enter-to,
.slide-fade-leave {
  @apply scale-100 opacity-100;
}

.slide-fade-enter-active,
.slide-fade-leave-active {
  @apply transition;
}
</style>
