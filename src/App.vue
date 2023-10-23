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

//list props需要的array
const dataObjArray = reactive([]);

//存放addpop emit資料的object
let dataObj = reactive({ text: "", color: "", amount: 0 });

//開啟/關閉AddPopWindow
const isAddPopDisplay = () => {
  isDisplayAdd.value = !isDisplayAdd.value;
  console.log("關閉/顯示addPopWindow");
};

//新增list表單
const addTranscation = () => {
  //array.push (object) --> []
  dataObjArray.push(dataObj);
  console.log("資料新增成功" + JSON.stringify(dataObj));

  //push進陣列後clear dataObj
  dataObj = { text: "", color: "", amount: 0 };

  //關閉addPopWIndow
  isAddPopDisplay();
};

//開啟/關閉DeletePopWindow，指定Button的父組件
const isDeletePopDisplay = () => {
  isDisplayDelete.value = !isDisplayDelete.value;
  console.log("關閉/顯示deletePopWindow");
};

//刪除list表單
const deleteTranscation = (index) => {
  //清除Array資料
  dataObjArray.splice(index, 1);
  console.log("資料刪除成功" + JSON.stringify(dataObj));

  //關閉彈跳視窗
  isDeletePopDisplay();
};

//取得addPop emit的資料
const setText = (data) => {
  // 將資料覆寫至dataObj修改原有資料
  dataObj.text = data;
};

const setColor = (data) => {
  // 將資料覆寫至dataObj修改原有資料
  dataObj.color = data;
};

const setAmount = (data) => {
  // 將資料覆寫至dataObj修改原有資料
  dataObj.amount = Number(data);
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
        <list
          v-for="(item, index) in dataObjArray"
          :text="item.text"
          :color="item.color"
          :amount="item.amount"
          :btnNum="index"
          :isDisplay="isDeletePopDisplay"
          :listArray="dataObjArray"
        />
      </div>
    </div>
  </div>

  <addPopWindow
    class="fixedground"
    v-if="isDisplayAdd"
    :isDisplay="isAddPopDisplay"
    :addBtn="addTranscation"
    @getText="setText"
    @getColor="setColor"
    @getAmount="setAmount"
  />

  <deletePopWindow
    class="fixedground"
    v-show="isDisplayDelete"
    :isDisplay="isDeletePopDisplay"
    :deleteList="deleteTranscation"
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
