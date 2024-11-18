<template>
    <div id="CosineLaw" class="dform">
        <h2 class="header">Cosine Law</h2>
            <form @submit.prevent="cosineLaw">
            <label class="lable" for="sideA">Side A:</label><br>
            <input class="number" v-model="sideA" type="number" required><br>
    
            <label class="lable" for="sideB">Side B:</label><br>
            <input class="number" v-model="sideB" type="number" required><br>
    
            <label class="lable" for="angleC">Angle C (in degrees):</label><br>
            <input class="number" v-model="angleC" type="number" required><br>
    
            <label class="lable" for="sideC">Side C (Result):</label><br>
            <input class="number" v-model="sideC" readonly><br>
    
            <button class="Calculate" type="submit">Calculate</button>
        </form>
        </div>
  </template>
  
  <script>
  export default {
    name: 'CosLaw',
    data() {
      return {
        sideA: null,
        sideB: null, 
        angleC: null,
        sideC: null,  
      };
    },
    methods: {
      cosineLaw() {
        const a = parseFloat(this.sideA);
        const b = parseFloat(this.sideB);
        const c = parseFloat(this.angleC);

        const angleCRadians = c * (Math.PI / 180);
  
        const result = Math.sqrt(Math.pow(a, 2) + Math.pow(b, 2) - 2 * a * b * Math.cos(angleCRadians));
  
        this.sideC = result.toFixed(2);
      }
    }
  };
  </script>
  
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
    margin-bottom: 30px;
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
  