<script setup>
const props = defineProps({
  isDisplay: {
    type: Function,
    default: () => {},
  },
});
</script>

<template>
  <div class="body">
    <span>Text</span>
    <div class="flexbox">
      <p>$0</p>
      <button @click="isDisplay">Delete</button>
    </div>
  </div>
</template>

<style scoped lang="scss">
.body {
  width: 35vw;
  border: 1px solid #3c7fa5;
  border-radius: 8px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem 1rem;

  span {
    font-size: 1.5rem;
  }

  .flexbox {
    display: flex;
    align-items: center;
    p {
      font-size: 1.5rem;
      margin-right: 1rem;
    }

    button {
      background-color: #3c7fa5;
      color: white;
      border-radius: 8px;
      border: none;
      padding: 0.5rem 1rem;
      font-size: 1.25rem;

      &:hover {
        cursor: pointer;
      }
    }
  }
}
</style>
