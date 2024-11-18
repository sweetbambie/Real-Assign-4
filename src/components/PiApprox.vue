<script setup>
import { ref } from 'vue';

const nValue = ref(null);
const piApproxValue = ref(null);

function piApprox() {
    const n = parseFloat(nValue.value);
    let pi = 0;

    for (let i = 0; i <= n; i++) {
        pi += Math.pow(-1, i) / ((2 * i) + 1);
      }
      piApproxValue.value = (pi * 4);
    }
</script>

<template>
    <div id="PiApprox" class="dform">
    <h2 class="header">Gregory-Leibniz Pi Approximation</h2>
    <form @submit.prevent="piApprox">
        <label for="nvalue">n Value:</label><br>
        <input class="number" v-model="nValue" id="Nvalue" name="nvalue" type="number"><br> 
        <label for="piapprox">Pi Approximation (Result):</label><br>
        <input class="number" v-model="piApproxValue" id="pi" name="pi" readonly><br>
        <button class="Calculate" type="button" @click="piApprox">Calculate</button>
    </form>
    </div>
</template>
  
<style scoped>
  .dform {
    border: 1px solid #ccc;
    border-radius: 5px;
    padding: 20px;
    background-color: lightpink;
    min-height: 250px;
    margin-top: 3%;
    height: 100%;
    color: black;
  }
  
  .header {
    text-align: center;
  }
  
  button {
    padding: 9px 19px;
    background-color: #f48dc1;
    color: rgb(255, 255, 255);
    border-radius: 3px;
    transition: background-color 0.2s;
    margin-top: 10px;
  }
  
  button:hover {
    background-color: #ac7373;
  }
  
  .number {
    margin-bottom: 5%;
    width: 97%;
    font-size: 17px;
    background-color: azure;
    color: black;
  }
  
  .Calculate {
    margin-bottom: 5%;
    width: 97%;
    font-size: 17px;
  }
  </style>
  