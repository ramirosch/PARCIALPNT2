<template>
  <div>
    <h1>Conversor de Temperatura</h1>

    <div>
      Ingrese Temperatura °C: 
      <input 
        type="number" 
        id="tempC" 
        v-model.number="tempC"
      >
    </div>

    <p :class="textClass">
      Conv Temperatura °F: {{ tempF }}
    </p>

    <p :class="textClass">
      Conv Temperatura °K: {{ tempK }}
    </p>

    <p>
      Respuestas: <br>
      1: @click <br>
      - 2: Los espacios adelante y atrás en una entrada de texto <br>
      - 3: Definir el path y el componente activo para esa ruta
    </p>

  </div>
</template>

<script>
export default {
  name: 'ConversorTemperatura',
  data() {
    return {
      tempC: 0
    };
  },
  computed: {
    tempF() {
      return ((Number(this.tempC) * 9 / 5) + 32).toFixed(2); 
    },
    tempK() {
      return (Number(this.tempC) + 273.15).toFixed(2);
    },

    textClass() {
      const temp = Number(this.tempC);
      if (temp <= 0) {
        return 'text-blue';
      } else if (temp > 0 && temp < 15) {
        return 'text-magenta'; 
      } else {
        return 'text-red';
      }
    }
  }
};
</script>

<style scoped>
.text-blue { color: blue !important; }
.text-magenta { color: magenta !important; }
.text-red { color: red !important; }

div {
  font-family: serif; 
  padding: 0; 
  text-align: left; 
  margin: 10px 0 0 0; 
  padding-left: 20px;
  font-size: 14px; 
}
h1 {
  font-family: serif; 
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 5px; 
  white-space: nowrap; 
  width: min-content;
}

div > div {
    margin-top: 5px;
    margin-bottom: 10px; 
}

input {
  border: 1px solid black;
  padding: 1px; 
  width: 50px; 
  text-align: right; 
}

p {
  margin: 2px 0; 
  line-height: 1.2; 
}

p:last-of-type {
    margin-top: 15px; 
}
</style>