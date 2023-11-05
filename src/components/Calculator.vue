<template>
  <section id="calculator">
    <input v-model="input">
    <br>
    <button @click="appendToInput('+')">+</button>
    <button @click="appendToInput('-')">-</button>
    <button @click="appendToInput('*')">*</button>
    <button @click="appendToInput('/')">/</button>
    <br>
    <button @click="clearInput">C</button>
    <button @click="calculateResult">=</button>
    <br>
    <div id="calculation">{{ input }}</div>
    <div id="total">{{ total }}</div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      input: '',
      calculation: '',
      total: '',
    };
  },
};
</script>

<style scoped>
</style>
