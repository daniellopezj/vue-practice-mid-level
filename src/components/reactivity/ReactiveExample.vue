<template>
  {{ a + b }}
  {{ c }}
</template>
<script setup>
import { computed, onErrorCaptured, ref } from "vue";

onErrorCaptured((err, instance, info) => {
  console.error('🧨 Error capturado:', err)
  console.log('📍 En el componente:', instance)
  console.log('ℹ️ Información extra:', info)
  // Devuelve true para detener la propagación, false para permitir que suba
  return false
})

const a = ref(3);
const b = ref(2);
const c = computed(() => a.value + b.value);
</script>
