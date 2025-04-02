<template>
  <label for="name">Name</label>
  <input id="name" v-model="objectOne.name" />

  this value: {{  newObject?.name }}
</template>
<script setup>
import { reactive, ref, watch } from "vue";

const objectOne = reactive({
  name: "John",
  age: 30,
  address: {
    city: "New York",
    country: "USA",
  },
});

const newObject =  ref(null)

watch(objectOne, (newValue) => {
  console.log("occurred a change", newValue.name);
  newObject.value = newValue
});

watch(newObject, (newValue) => {
console.log('cambio new object', newValue.address)
});

</script>
<style scoped></style>
