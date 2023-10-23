<script setup>
const props = defineProps({
  isDisplay: {
    type: Function,
    default: () => {},
  },
  addBtn: {
    type: Function,
    default: () => {},
  },
});

const emits = defineEmits(["getText", "getColor", "getAmount"]);
</script>

<template>
  <div class="body">
    <form action="">
      <i class="fa-solid fa-x icon" @click="isDisplay"></i>
      <label for="">Text</label>
      <input
        type="text"
        placeholder="Empty"
        @change="$emit(`getText`, $event.target.value)"
      />

      <div class="radioBox">
        <input
          type="radio"
          name="chooseColor"
          value="green"
          @input="$emit(`getColor`, $event.target.value)"
        />
        <label for="">income</label>
        <input
          type="radio"
          name="chooseColor"
          value="red"
          @input="$emit(`getColor`, $event.target.value)"
        />
        <label for="">expense</label>
      </div>

      <label for="">Amount</label>
      <input
        type="number"
        placeholder="Empty"
        @change="$emit(`getAmount`, $event.target.value)"
      />
      <button type="button" @click="addBtn">add transaction</button>
    </form>
  </div>
</template>

<style scoped lang="scss">
label {
  font-size: 1.5rem;
  color: #3c7fa5;
}

input {
  border-radius: 8px;
  border: 1px solid #3c7fa5;
  padding: 0.5rem 1rem;
}
.body {
  background-color: rgba(0, 0, 0, 0.5);
  height: 100vh;
  width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;

  form {
    background-color: white;
    width: 30vw;
    height: 50vh;
    padding: 2rem;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    position: relative;
    border-radius: 12px;

    .icon {
      position: absolute;
      top: 3%;
      right: 3%;
      font-size: 1.5rem;
      color: #3c7fa5;

      &:hover {
        cursor: pointer;
      }
    }

    .radioBox {
      display: flex;
      justify-content: space-around;
      align-items: center;
      margin: 1rem 0;

      input {
        height: 1rem;
        width: 1rem;
      }
    }

    button {
      width: 60%;
      align-self: center;
      background-color: #3c7fa5;
      color: white;
      border-radius: 8px;
      border: none;
      padding: 0.5rem 1rem;
      margin-top: 1rem;
      font-size: 1.25rem;

      &:hover {
        cursor: pointer;
      }
    }
  }
}
</style>
