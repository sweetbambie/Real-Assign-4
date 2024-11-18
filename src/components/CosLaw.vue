<script setup>
import { ref } from 'vue';

// Declare reactive state using ref
const sideA = ref(null);
const sideB = ref(null);
const sideC = ref('');  // To store the result
const angleC = ref(null);  // Angle C in degrees

// Method to calculate the side C using the cosine law
function cosineLaw() {
  // Access the values of sideA, sideB, and angleC using .value
  const a = parseFloat(sideA.value);  // side A
  const b = parseFloat(sideB.value);  // side B
  const c = parseFloat(angleC.value);  // Angle C in degrees
  
  // If any value is invalid, return
  if (isNaN(a) || isNaN(b) || isNaN(c)) {
    sideC.value = 'Invalid input';
    return;
  }

  // Convert angle C from degrees to radians
  const angleCRadians = c * (Math.PI / 180);

  // Apply the cosine law formula
  const result = Math.sqrt(Math.pow(a, 2) + Math.pow(b, 2) - 2 * a * b * Math.cos(angleCRadians));

  // Set the result with 2 decimal places
  sideC.value = result.toFixed(2);
}
</script>

<template>
  <div id="CosineLaw" class="dform">
    <h2 class="header">Cosine Law</h2>
    <form @submit.prevent="cosineLaw">
      <!-- Side A Input -->
      <label class="lable" for="sideA">Side A:</label><br>
      <input class="number" v-model="sideA" type="number" required /><br>

      <!-- Side B Input -->
      <label class="lable" for="sideB">Side B:</label><br>
      <input class="number" v-model="sideB" type="number" required /><br>

      <!-- Angle C Input -->
      <label class="lable" for="angleC">Angle C (in degrees):</label><br>
      <input class="number" v-model="angleC" type="number" required /><br>

      <!-- Side C Output -->
      <label class="lable" for="sideC">Side C (Result):</label><br>
      <input class="number" v-model="sideC" readonly /><br>

      <!-- Submit Button -->
      <button class="Calculate" type="submit">Calculate</button>
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
  