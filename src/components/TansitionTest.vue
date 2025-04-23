<template>
  <div>
    <h1>transition</h1>
    <transition>
      <p v-if="show">transition</p>
    </transition>
    <button @click="show = !show">Toggle</button>
  </div>
</template>
<script setup>
import { ref } from "vue";
const show = ref(true);
</script>
<style scoped>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
