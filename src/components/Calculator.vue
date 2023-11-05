<template>
  <section id="calculator" class="bg-white p-10">
    <div class="flex flex-col justify-center p-7 border-[#013562] border-2 rounded-lg mb-5">
      <input v-model="numericInput" @input="validateNumericInput" type="text" class="text-2xl border-[#013562] border-2 mx-auto mb-5 p-5 h-[75px] w-full max-w-[250px]">
      <div class="flex justify-center mb-5">
        <button class="bg-[#013562] text-white text-lg mx-1 w-[75px] h-[50px]" @click="appendToInput('+')">+</button>
        <button class="bg-[#013562] text-white text-lg mx-1 w-[75px] h-[50px]" @click="appendToInput('-')">-</button>
        <button class="bg-[#013562] text-white text-lg mx-1 w-[75px] h-[50px]" @click="appendToInput('*')">*</button>
        <button class="bg-[#013562] text-white text-lg mx-1 w-[75px] h-[50px]" @click="appendToInput('/')">/</button>
      </div>
    </div>
    <div class="flex flex-col justify-center p-7 border-[#013562] border-2 rounded-lg">
      <div id="calculation" class="text-[#013562] font-bold text-3xl text-center mb-5 break-words">{{ calculation ? calculation : 0 }}</div>
      <div id="total" class="text-[#013562] font-bold text-3xl text-center break-words">Result: {{ total }}</div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      numericInput: '',
      calculation: '',
      total: null,
    }
  },
  methods: {
    validateNumericInput() {
      // Remove any non-numeric characters
      this.numericInput = this.numericInput.replace(/[^0-9]/g, '')
    },
    appendToInput(operator) {
      if (this.numericInput) {
        this.calculation += this.numericInput + operator
        // Clear the numeric input
        this.numericInput = ''
        // Calculate the total after appending an operator
        this.calculateTotal()
      }
    },
    calculateTotal() {
      let calculation = this.calculation;
      if (calculation.endsWith('+') || calculation.endsWith('-') || calculation.endsWith('*') || calculation.endsWith('/')) {
        // Remove the trailing operator
        calculation = calculation.slice(0, -1);
      }
      try {
        // Evaluate the total
        this.total = eval(calculation);
      } catch (error) {
        this.total = 'Error';
      }
    },
  },
};
</script>
