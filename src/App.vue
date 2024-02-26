<script setup>
import APIComponent from './components/APIComponent.vue';
import Calculator from './components/Calculator.vue';
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div class="main">
    <Calculator />
    <APIComponent />
  </div>
</template>

<style scoped>
.main {
  display: flex;
  justify-content: space-around;
}
</style>
