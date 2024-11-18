<template>
  <div class="grid-container">
    <CosLaw />
    <Asymptote />
    <PiApprox />
  </div>
</template>

<script>
import CosLaw from './components/CosLaw.vue';
import Asymptote from './components/Asymptote.vue';
import PiApprox from './components/PiApprox.vue';

export default {
  name: 'App',
  components: {
    CosLaw,
    Asymptote,
    PiApprox
  }
};
</script>

<style>
body {
  background-color: rgb(255, 213, 225);
  color: #000000;
  padding: 20px;
  gap: 20px;
  padding: 20px;
  margin-bottom: 30px;
}

.grid-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);  
  gap: 5%; 
  width: 80%; 
  margin: 0 auto;  
}

.grid-container > * {
  margin-bottom: 20px;
}
</style>