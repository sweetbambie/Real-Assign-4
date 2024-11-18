<template>
    <div id="Asymptote" class="dform">
    <h2 class="header">Asymptote Finder</h2>
    <form @submit.prevent="asymptote">
        <label for="mvalue">m Value:</label><br>
        <input class="number" v-model="mvalue" id="mvalue" name="mvalue" type="number" /><br>
        
        <label for="nvalue">n Value:</label><br>
        <input class="number" v-model="nvalue" id="nvalue" name="nvalue" type="number" /><br>
        
        <label for="atype">Asymptote Type (Result):</label><br>
        
        <input class="number" v-model="atype" id="atype" name="atype" readonly /><br>
        <button class="Calculate" type="submit">Calculate</button>
    </form>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Asymptote',
    data() {
      return {
        mvalue: null,  
        nvalue: null, 
        atype: '',    
      };
    },
    methods: {
      asymptote() {
        const m = parseFloat(this.mvalue);
        const n = parseFloat(this.nvalue);

        if (m === n) {
          this.atype = "The asymptote is horizontal";
        } else if (n > m) {
          this.atype = "The asymptote is the x-axis";
        } else if (m > n) {
          const difference = m - n;
          switch (difference) {
            case 1:
              this.atype = "Linear";
              break;
            case 2:
              this.atype = "Quadratic";
              break;
            case 3:
              this.atype = "Cubic";
              break;
            case 4:
              this.atype = "Quartic";
              break;
            case 5:
              this.atype = "Quintic";
              break;
            case 6:
              this.atype = "Sextic";
              break;
            case 7:
              this.atype = "Septic";
              break;
            case 8:
              this.atype = "Octic";
              break;
            case 9:
              this.atype = "Nonic";
              break;
            case 10:
              this.atype = "Decic";
              break;
            default:
              this.atype = "Undefined";
              break;
          }
        }
      },
    },
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