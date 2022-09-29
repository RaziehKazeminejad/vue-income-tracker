<template>
  <div class="relative flex py-4 pr-4 bg-white rounded-lg max-w-xl mb-8 mx-auto">
    <div class="text-red-600 font-semibold text-xl leading-4 text-center mx-4 my-1" @click="removeItem">x</div>
    <div class="text-gray-400 flex-1 text-xl">
      {{ income.desc }}
    </div>
    <div class="text-gray-500 flex-1 text-xl">
      £{{ income.value }}
    </div>
    <div class="text-gray-500 text-right text-xl">
      {{ formattedDate }}
    </div>
  </div>
</template>

<script>
export default {
  props: {
    income: Object
  },
  setup (props, { emit }) {
    
    const date = new Date(props.income.date);
    const day = date.getDate();
    const month = date.getMonth();
    const year = date.getFullYear();

    const formattedDate = day + "/" + month + "/" + year;

    function removeItem () {
      emit("remove-item", props.income.id);
    }

    return {
      formattedDate,
      removeItem
    }
  }
}
</script>