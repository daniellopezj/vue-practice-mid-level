<template>
  <div class="reactive-test"> 
    
    <h1>reactive</h1>
    <div>
      <label for="name">Name</label>
      <input id="name" v-model="objectOne.name" />
      this value: {{ newObject.name }}
    </div>
    <div>
      <label for="input-uno">REF</label>
      <input ref="uno" id="input-uno"  />
    </div>
    <div>
      <label for="input-uno">useTemplateRef</label>
      <input ref="dos" id="input-dos"  />
    </div>

  </div>
</template>

<script setup>
import { reactive, ref, watch, useTemplateRef } from "vue";

const objectOne = reactive({
  name: "John",
  age: 30,
  address: {
    city: "New York",
    country: "USA",
  },
});

const uno = ref(null);
const dos = useTemplateRef('dos');

const newObject = ref({});

watch(uno, (newValue) => {
  console.log("changes uno", newValue);
});
watch(dos, (newValue) => {
  console.log("changes dos", newValue);
});

watch(objectOne, (newValue) => {
  console.log("occurred a change", newValue.name);
  newObject.value = { ...newValue }; // puedes hacer copia si necesitas desvincularlo
}, { deep: true });



watch(newObject, (newValue) => {
  console.log("cambio new object", newValue.address);
});
</script>

<style scoped lang="css">
.reactive-test {
 display: grid;
 grid-template-columns: 1fr;
} 
</style>