<script setup>
import { ref, computed, onMounted } from 'vue'

const firstName = ref('John')
const lastName = ref('Doe')

const fullName = computed({
  get() {
    return firstName.value + ' jhjjh ' + lastName.value
  },
  set(newValue) {
    [firstName.value, lastName.value] = newValue.split(' ')
  }
})

onMounted(() => {
  setTimeout(() => {
    fullName.value = 'una prueba'
  }, 5000);
})
</script>

<template>
<div>
  {{  fullName }}
</div>
</template>