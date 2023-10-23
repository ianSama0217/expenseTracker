<script setup>
const props = defineProps({
  text: {
    type: String,
    default: "",
  },
  color: {
    type: String,
    default: "",
  },
  amount: {
    type: Number,
    default: 0,
  },
  btnNum: Number,

  isDisplay: {
    type: Function,
    default: () => {},
  },
  listArr: {
    type: Array,
    default: () => [],
  },
});
</script>

<template>
  <div class="body">
    <span>{{ text }}</span>
    <div class="flexbox">
      <p :class="color">$ {{ amount }}</p>
      <button @click="isDisplay" id="targetList">Delete{{ btnNum }}</button>
    </div>
  </div>
</template>

<style scoped lang="scss">
.red {
  color: #a53c42;
}

.green {
  color: #70a53c;
}
.body {
  width: 35vw;
  border: 1px solid #3c7fa5;
  border-radius: 8px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem 1rem;
  margin-top: 1rem;

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
