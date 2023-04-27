<script setup lang="ts">
import logo from "./logo.vue";

const firstMenuLineRef = ref();
const secondMenuLineRef = ref();

const startMenuAnimation = () => {
  firstMenuLineRef.value.classList.remove("running-right");
  firstMenuLineRef.value.classList.add("running-left");
  secondMenuLineRef.value.classList.remove("running-left");
  secondMenuLineRef.value.classList.add("running-right");
};

const endMenuAnimation = () => {
  firstMenuLineRef.value.classList.remove("running-left");
  firstMenuLineRef.value.classList.add("running-right");
  secondMenuLineRef.value.classList.remove("running-right");
  secondMenuLineRef.value.classList.add("running-left");
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
        <div class="first_menu_line">
          <p ref="firstMenuLineRef">ME</p>
        </div>
        <div class="second_menu_line">
          <p ref="secondMenuLineRef">NU</p>
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

.first_menu_line {
  width: 50px;
  overflow: hidden;
}

.second_menu_line {
  margin-left: 22px;
  width: 50px;
  overflow: hidden;
}

.running-left {
  animation: running-left 0.3s linear forwards;
}
.running-right {
  animation: running-right 0.3s linear forwards;
}

@keyframes running-left {
  0% {
    transform: translateX(0);
  }
  50% {
    transform: translateX(100%);
  }
  51% {
    transform: translateX(-100%);
  }
  100% {
    transform: translateX(0);
  }
}

@keyframes running-right {
  0% {
    transform: translateX(0);
  }
  50% {
    transform: translateX(-100%);
  }
  51% {
    transform: translateX(100%);
  }
  100% {
    transform: translateX(0);
  }
}
</style>
