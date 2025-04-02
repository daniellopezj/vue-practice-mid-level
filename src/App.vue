
<script setup>
import WatchTest from './components/WatchTest.vue'
import ComputedTest from './components/ComputedTest.vue'
import ParentSlot from './components/slots/ParentSlot.vue'
import TansitionTest from './components/TansitionTest.vue'
import ReactiveTest from './components/reactivity/ReactiveTest.vue'
import {  useRouter } from 'vue-router'

const router= useRouter()

const navigateTo = (path)=>{
  router.push(path)
}
</script>

<template>
<div>
  Esto es una prueba
  <span @click="navigateTo('/')" >Home</span>
  <span @click="navigateTo('contact')" >Contacto</span>
  <RouterView />

  <!-- <WatchTest />
  <ComputedTest />
  <ParentSlot />
  <TansitionTest />
  <ReactiveTest /> -->
</div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
