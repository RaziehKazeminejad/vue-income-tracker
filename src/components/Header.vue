<template>
  <header class="flex justify-between items-center px-8 py-4 bg-gray-800 border-b-4 border-yellow-400">
    <h1 class=" text-white text-3xl">Income Tracker</h1>
    <div class="bg-yellow-400 text-white text-xl font-black px-3 py-2 min-w-max text-center rounded-lg shadow-inner drop-shadow-lg shadow-black">£{{ totalIncome }}</div>
  </header>
</template>

<script>
export default {
  props: {
    totalIncome: Number
  }
}
</script>
