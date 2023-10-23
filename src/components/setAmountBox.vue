<script setup>
const props = defineProps({
  totalIncome: {
    type: Number,
    default: 0,
  },
  totalExpense: {
    type: Number,
    default: 0,
  },
});
</script>

<template>
  <div class="body">
    <div class="totalIncome">
      <span>INCOME</span>
      <p>$ {{ totalIncome }}</p>
    </div>
    <div class="totalExpense">
      <span>EXPENSE</span>
      <p>$ {{ totalExpense }}</p>
    </div>
  </div>
</template>

<style scoped lang="scss">
span {
  font-size: 1.5rem;
}

p {
  font-size: 2rem;
  margin-top: 0.5rem;
}
.body {
  width: 40vw;
  display: flex;
  justify-content: space-between;

  .totalIncome {
    color: #70a53c;
  }

  .totalExpense {
    color: #a53c42;
  }
}
</style>
