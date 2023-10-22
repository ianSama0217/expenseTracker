<script setup>
import sidebar from "./components/sidebar.vue";
import setAmountBox from "./components/setAmountBox.vue";
import addBtn from "./components/addBtn.vue";
import list from "./components/list.vue";
import addPopWindow from "./components/addPopWindow.vue";
import deletePopWindow from "./components/deletePopWindow.vue";
</script>

<template>
  <div class="body">
    <div class="leftBox">
      <sidebar />
    </div>

    <div class="rightBox">
      <div class="rightTopBox">
        <setAmountBox />
        <addBtn />
      </div>
      <div class="listArea">
        <list />
      </div>
    </div>
  </div>

  <!-- <addPopWindow /> -->
  <!-- <deletePopWindow /> -->
</template>

<style scoped lang="scss">
.body {
  display: flex;

  .leftBox {
    flex: 1 1 30vw;
  }

  .rightBox {
    flex: 3 1 50vw;
    display: flex;
    flex-direction: column;
    padding-top: 10vh;
    padding-left: 10vw;

    .rightTopBox {
      height: 30vh;
      width: 40vw;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    .listArea {
      height: 50vh;
      width: 40vw;
      margin-top: 1rem;
      padding: 1rem;
      overflow-y: scroll;
    }
  }
}
</style>
