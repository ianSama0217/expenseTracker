<script setup></script>

<template>
  <div class="body">
    <h1>Expense Tracker</h1>
    <h3>Kouhei</h3>
    <div class="totalBalance">
      <span>YOUR BALANCE</span>
      <p>$0</p>
    </div>
  </div>
</template>

<style scoped lang="scss">
.body {
  height: 100vh;
  width: 30vw;
  background-color: #3c7fa5;
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;

  h1 {
    font-size: 2.5rem;
  }

  h3 {
    font-size: 2rem;
  }

  span {
    font-size: 1.5rem;
  }
  p {
    margin: 1rem 0;
    font-size: 2rem;
  }
}
</style>
