<template>
  <div class="mt-8 p-4">
    <IncomeItem
      v-for="obj in state.sortedIncome"
      :key="obj.id"
      :income="obj"
      @remove-item="removeItem"
    />
  </div>
</template>

<script>
import IncomeItem from "./IncomeItem";

export default {
  components: {
    IncomeItem,
  },
  props: {
    state: Object,
  },
  setup(props, { emit }) {
    function removeItem(id) {
      emit("remove-item", id);
    }

    return {
      IncomeItem,
      removeItem,
    };
  },
};
</script>