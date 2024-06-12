<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div>
      <label for="number1">Número 1:</label>
      <input type="number" id="number1" v-model.number="number1">
    </div>
    <div>
      <label for="number2">Número 2:</label>
      <input type="number" id="number2" v-model.number="number2">
    </div>
    <div>
      <label for="operation">Operação:</label>
      <select id="operation" v-model="operation">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
    </div>
    <div>
      <h2>Resultado: {{ result }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: '+'
    }
  },
  computed: {
    result() {
      switch (this.operation) {
        case '+':
          return this.number1 + this.number2;
        case '-':
          return this.number1 - this.number2;
        case '*':
          return this.number1 * this.number2;
        case '/':
          return this.number1 / this.number2;
        default:
          return 0;
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

label {
  margin-right: 10px;
}

input, select {
  margin-bottom: 20px;
}
</style>
