<script setup>
const props = defineProps({
  isDisplay: {
    type: Function,
    default: () => {},
  },
  deleteList: {
    type: Function,
    default: () => {},
  },
});
</script>

<template>
  <div class="body">
    <div class="deletebox">
      <i class="fa-solid fa-x icon" @click="isDisplay"></i>
      <span for="">Sure to delete?</span>
      <button type="button" @click="deleteList">Delete</button>
    </div>
  </div>
</template>

<style scoped lang="scss">
.body {
  background-color: rgba(0, 0, 0, 0.5);
  height: 100vh;
  width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;

  .deletebox {
    background-color: white;
    width: 30vw;
    height: 40vh;
    padding: 2rem;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    position: relative;
    border-radius: 12px;

    span {
      font-size: 2rem;
      color: #3c7fa5;
    }

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

    button {
      width: 60%;
      background-color: #a53c42;
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
