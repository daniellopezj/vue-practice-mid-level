<script setup>
import ChildSlot from './ChildSlot.vue'
</script>

<template>

  <h1>parent slot</h1>
 
  <ChildSlot>
    <template #header>
      <h1>This is the header</h1>
    </template>

    <!-- <template #default>
      <p>This is the content</p>
    </template> -->

    <template #footer>
      <em>This is the footer</em>
    </template>
  </ChildSlot>
</template>
