<script setup lang="ts">
import logo from "./logo.vue";
</script>

<template>
  <div class="nav_container">
    <logo />
    <div class="menu_container">
      <button class="watch_button">watch smth</button>
      <div class="menu_title">
        <p>ME</p>
        <p class="second_line">NU</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
@import "./utilities/common.css";
.nav_container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  font-family: var(--general-font);
  color: var(--general-text-color);
  padding-top: 40px;
}

.menu_container {
  width: 280px;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  padding-right: 30px;
}

.watch_button {
  background-color: var(--general-text-color);
  color: var(--general-bg-color);
  display: flex;
  width: 10.4375em;
  height: 4.9375em;
  justify-content: center;
  align-items: center;
  flex: 0 0 auto;
  border-radius: 100vw;
  font-size: 1rem;
  letter-spacing: -0.02em;
  border: none;
}

.menu_title {
  font-size: 34px;
}

.second_line {
  padding-left: 22px;
}
</style>
