<script setup lang="ts">
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
  secondMenuLineRef.value.style.transform = `translateX(0)`;
};
</script>

<template>
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
</template>

<style>
.menu_title {
  font-size: 34px;
  cursor: pointer;
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
  transition: transform 0.2s linear;
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
  transition: transform 0.2s linear;
}
</style>
