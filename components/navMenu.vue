<script setup lang="ts">
import logo from "./logo.vue";

const firstMenuLineRef = ref();
const secondMenuLineRef = ref();
let firstMenuLinePos = 0;
let secondMenuLinePos = 0;

const startMenuAnimation = () => {
  firstMenuLinePos = firstMenuLineRef.value.getBoundingClientRect().width;
  secondMenuLinePos = secondMenuLineRef.value.getBoundingClientRect().width;
  firstMenuLineRef.value.style.transform = `translateX(${
    firstMenuLinePos + 8
  }px)`;
  secondMenuLineRef.value.style.transform = `translateX(-${
    secondMenuLinePos + 10
  }px)`;
};

const endMenuAnimation = () => {
  firstMenuLineRef.value.style.transform = `translateX(0)`;
  secondMenuLineRef.value.style.transform = `translateX(0%)`;
};
</script>

<template>
  <div class="nav_container">
    <logo />
    <div class="menu_container">
      <button class="watch_button">watch smth</button>
      <div
        class="menu_title"
        @mouseover="startMenuAnimation"
        @mouseleave="endMenuAnimation"
      >
        <div class="first_menu_line_container">
          <p class="first_menu_line" ref="firstMenuLineRef">ME ME</p>
        </div>
        <div class="second_menu_line_container">
          <p class="second_menu_line" ref="secondMenuLineRef">NU NU</p>
        </div>
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

.first_menu_line_container {
  width: 50px;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}
.first_menu_line {
  position: relative;
  left: -60px;
  transition: transform 0.3s linear;
}

.second_menu_line_container {
  width: 50px;
  margin-left: 22px;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.first_menu_line_container:hover .first_menu_line {
  transform: translateX(-100%);
}

.second_enu_line_container:hover .second_menu_line {
  transform: translateX(100%);
}

.second_menu_line {
  position: relative;
  left: 0;
  transition: transform 0.3s linear;
}
</style>
