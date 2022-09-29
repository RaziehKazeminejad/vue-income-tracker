<template>
  <form class="flex justify-center mt-8" @submit.prevent="FormHandler">
    <input type="text" placeholder="Income Description..." v-model="formData.desc" class="block py-1 px-4 text-gray-500 border-none rounded-l-lg outline-none text-xl placeholder:text-slate-100 placeholder:italic" />
    <input type="number" placeholder="Income Value..." v-model="formData.value" class="block py-1 px-4 text-gray-500 border-none outline-none text-xl placeholder:text-slate-100 placeholder:italic" />
    <input type="date" placeholder="Income Date..." v-model="formData.date" class="block py-1 px-4 text-gray-500 border-none outline-none text-xl placeholder:text-slate-100 placeholder:italic" />
    <input type="submit" value="SUBMIT" class="block border-none rounded-r-lg outline-none text-white font-medium shadow-lg shadow-cyan-500/50 py-1 px-4 bg-yellow-400 cursor-pointer" />
  </form>
</template>

<script>
import { reactive } from 'vue';

export default {
  props: {
    state: Object
  },
  setup (props, { emit }) {
    const formData = reactive({
      desc: null,
      value: null,
      date: null
    });

    function FormHandler () {
      emit("add-income", {
        desc: formData.desc,
        value: formData.value,
        date: formData.date
      });
      
      formData.desc = null;
      formData.value = null;
      formData.date = null;
    }
    return {
      FormHandler,
      formData
    }
  }
}
</script>

