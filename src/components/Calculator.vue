<template>
  <section id="calculator" class="bg-white p-10">
    <div class="flex flex-col justify-center p-7 border-[#013562] border-2 rounded-lg mb-5">
      <input v-model="input" type="number" class="text-2xl border-[#013562] border-2 mx-auto mb-5 p-5 h-[75px] w-full max-w-[250px]">
      <div class="flex justify-center mb-5">
        <button class="bg-[#013562] text-white text-lg mx-1 w-[75px] h-[50px]" @click="appendToInput('+')">+</button>
        <button class="bg-[#013562] text-white text-lg mx-1 w-[75px] h-[50px]" @click="appendToInput('-')">-</button>
        <button class="bg-[#013562] text-white text-lg mx-1 w-[75px] h-[50px]" @click="appendToInput('*')">*</button>
        <button class="bg-[#013562] text-white text-lg mx-1 w-[75px] h-[50px]" @click="appendToInput('/')">/</button>
      </div>
      <div class="flex justify-center hidden">
        <button class="bg-[#013562] text-white text-lg mx-1 w-[75px] h-[50px]" @click="clearInput">C</button>
        <button class="bg-[#013562] text-white text-lg mx-1 w-[75px] h-[50px]" @click="calculateResult">=</button>
      </div>

    </div>
    <div class="flex flex-col justify-center p-7 border-[#013562] border-2 rounded-lg">
      <div id="calculation" class="text-[#013562] font-bold text-3xl text-center mb-5 break-words">{{ input ? input : '0' }}</div>
      <div id="total" class="text-[#013562] font-bold text-3xl text-center break-words">Result {{ total }}</div>
    </div>
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