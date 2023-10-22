<script setup>
import { ref, reactive } from "vue";
//匯入組件
import sidebar from "./components/sidebar.vue";
import setAmountBox from "./components/setAmountBox.vue";
import addBtn from "./components/addBtn.vue";
import list from "./components/list.vue";
import addPopWindow from "./components/addPopWindow.vue";
import deletePopWindow from "./components/deletePopWindow.vue";

const isDisplayDelete = ref(false);
const isDisplayAdd = ref(false);

//開啟/關閉DeletePopWindow
const isDeletePopDisplay = () => {
  isDisplayDelete.value = !isDisplayDelete.value;
  console.log("關閉/顯示deletePopWindow");
};

//開啟/關閉AddPopWindow
const isAddPopDisplay = () => {
  isDisplayAdd.value = !isDisplayAdd.value;
  console.log("關閉/顯示addPopWindow");
};
</script>

<template>
  <div class="body">
    <div class="leftBox">
      <sidebar />
    </div>

    <div class="rightBox">
      <div class="rightTopBox">
        <setAmountBox />
        <addBtn :isDisplay="isAddPopDisplay" />
      </div>
      <div class="listArea">
        <list :isDisplay="isDeletePopDisplay" />
      </div>
    </div>
  </div>

  <addPopWindow
    class="fixedground"
    v-show="isDisplayAdd"
    :isDisplay="isAddPopDisplay"
  />

  <deletePopWindow
    class="fixedground"
    v-show="isDisplayDelete"
    :isDisplay="isDeletePopDisplay"
  />
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

.fixedground {
  position: fixed;
  top: 0%;
}
</style>
