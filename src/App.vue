<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div>
      <input v-model.number="num1" type="number" placeholder="Número 1" />
      <select v-model="operation">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">*</option>
        <option value="divide">/</option>
      </select>
      <input v-model.number="num2" type="number" placeholder="Número 2" />
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
      num1: 0,
      num2: 0,
      operation: 'add',
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case 'add':
          return this.num1 + this.num2;
        case 'subtract':
          return this.num1 - this.num2;
        case 'multiply':
          return this.num1 * this.num2;
        case 'divide':
          return this.num2 !== 0 ? this.num1 / this.num2 : 'Erro: Divisão por zero';
        default:
          return 0;
      }
    },
  },
};
</script>

<style scoped>
#app {
  text-align: center;
  margin-top: 250px;
}

input {
  margin: 0 10px;
}

select {
  margin: 0 10px;
}
</style>
