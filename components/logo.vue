<script setup>
import { ref } from "vue";
const firstLineRef = ref();
const secondLineRef = ref();
let firstLinePos = 0;
let secondLinePos = 0;;

const startLogoAnimation = () => {
  firstLinePos = firstLineRef.value.getBoundingClientRect().width;
  secondLinePos = secondLineRef.value.getBoundingClientRect().width;
  firstLineRef.value.style.transform = `translateX(${firstLinePos}px)`;
  secondLineRef.value.style.transform = `translateX(-${secondLinePos + 4}px)`;
};

const endLogoAnimation = () => {
  firstLineRef.value.style.transform = `translateX(0)`;
  secondLineRef.value.style.transform = `translateX(0%)`;
};
</script>

<template>
  <div
    class="logo"
    @mouseover="startLogoAnimation"
    @mouseleave="endLogoAnimation"
  >
    <div class="first_line_container">
      <p class="first_line" ref="firstLineRef">PORT PORT</p>
    </div>
    <div class="second_line_container">
      <p class="second_line" ref="secondLineRef">FOLIO FOLIO</p>
    </div>
  </div>
</template>

<style scoped>
.logo {
  display: flex;
  flex-direction: column;
  margin-left: 40px;
  font-weight: 400;
  font-size: 30px;
}

.first_line_container {
  width: 90px;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}
.first_line {
  position: relative;
  left: -90px;
  transition: transform 0.3s linear;
}

.second_line_container {
  width: 94px;
  margin-left: 28px;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.first_line_container:hover .first_line {
  transform: translateX(-100%);
}

.second_line_container:hover .second_line {
  transform: translateX(100%);
}

.second_line {
  position: relative;
  left: 0;
  transition: transform 0.3s linear;
}
</style>
