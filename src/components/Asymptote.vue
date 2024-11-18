<script setup>
import { ref } from 'vue';

const mvalue = ref(null);
const nvalue = ref(null);
const atype = ref('');

function asymptote() {
  const m = parseFloat(mvalue.value);
  const n = parseFloat(nvalue.value);

  if (m === n) {
    atype.value = "The asymptote is horizontal.";
  } else if (n > m) {
    atype.value = "The asymptote is the x-axis.";
  } else if (m > n) {
    const difference = m - n;
    switch (difference) {
      case 1:
        atype.value = "Linear";
        break;
      case 2:
        atype.value = "Quadratic";
        break;
      case 3:
        atype.value = "Cubic";
        break;
      case 4:
        atype.value = "Quartic";
        break;
      case 5:
        atype.value = "Quintic";
        break;
      case 6:
        atype.value = "Sextic";
        break;
      case 7:
        atype.value = "Septic";
        break;
      case 8:
        atype.value = "Octic";
        break;
      case 9:
        atype.value = "Nonic";
        break;
      case 10:
        atype.value = "Decic";
        break;
      default:
        atype.value = "Undefined asymptote type.";
        break;
    }
  }
}
</script>

<template>
  <div id="Asymptote" class="dform">
    <h2 class="header">Asymptote Finder</h2>
    <form @submit.prevent="asymptote">
        <label for="mvalue">m Value:</label><br>
        <input class="number" v-model="mvalue" id="mvalue" name="mvalue" type="number" required /><br>
        <label for="nvalue">n Value:</label><br>
        <input class="number" v-model="nvalue" id="nvalue" name="nvalue" type="number" required /><br>
        <label for="atype">Asymptote Type (Result):</label><br>
        <input class="number" v-model="atype" id="atype" name="atype" type="text" readonly /><br>
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