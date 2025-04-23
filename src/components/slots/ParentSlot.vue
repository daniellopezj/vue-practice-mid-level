<script setup>
import ChildSlot from "./ChildSlot.vue";
</script>

<template>
  <div>
    <h1>slot</h1>

    <ChildSlot>
      <template #header>
        <h4>This is the header</h4>
      </template>

      <!-- <template #default>
      <p>This is the content</p>
    </template> -->

      <template #footer>
        <em>This is the footer</em>
      </template>
    </ChildSlot>
  </div>
</template>
