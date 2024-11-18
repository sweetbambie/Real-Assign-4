<script setup>
import CosLaw from './components/CosLaw.vue';
import Asymptote from './components/Asymptote.vue';
import PiApprox from './components/PiApprox.vue';
</script>

<template>
  <div class="grid-container">
    <CosLaw />
    <Asymptote />
    <PiApprox />
  </div>
</template>

<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr); 
  gap: 5%;  
  width: 80%; 
  margin: 0 auto;  
}
</style>