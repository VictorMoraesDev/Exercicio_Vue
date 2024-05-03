<script setup>

</script>

<template>
  <div id="app" class="container mt-5">
<h1 class="text-center mb-4">Calculadora Vue.JS</h1>

<div class="row justify-content-center">
  <div class="col-md-4">
<input v-model.number="num1" type="number" class="form-control" placeholder="Número 1">
</div>

<div class="col-md-4">
<input v-model.number="num2" type="number" class="form-control" placeholder="Número 2">
</div>
</div>

<div class="row justify-content-center mt-3">
  <div class="col-md-8">
<select v-model="operation" class="form-select">
<option value="add">+</option>
<option value="subtract">-</option>
<option value="multiply">*</option>
<option value="divide">/</option>
</select>
</div>
</div>

<div class="row justify-content-center mt-4">
  <div class="col-md-8">
  Restultado: {{ calculate() }}
</div>
</div>

  </div>
</template>

<script>

export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: 'add'
    };
  },
  methods: {
    calculate() {
      switch (this.operation) {
        case 'add':
          return this.num1 + this.num2;
          case 'subtract':
            return this.num1 - this.num2;
            case 'multiply':
              return this.num1 * this.num2;
              case 'divide':
                return this.num2 !== 0 ? this.num1 / this.num2 : 'Divisão de zero';
                default:
                  return 0;
      }
    }
  }
}

</script>

<style scoped>
#app {
  max-width: 600px;
  margin: 50px auto;
  text-align: center;
}
input, select {
  margin: 10px;
  padding: 10px;
  font-size: 16px;
}

</style>
