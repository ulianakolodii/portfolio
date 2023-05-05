<script setup lang="ts">
import { ref, onMounted } from "vue";

const watchButtonRef = ref();
const watchTitleRef = ref();
let prevX = 0;
let prevY = 0;
let currX = 0;
let currY = 0;

onMounted(() => {
  watchButtonRef.value.addEventListener("mousemove", (event: MouseEvent) => {
    prevX = currX;
    prevY = currY;
    currX = event.clientX;
    currY = event.clientY;
  });
});

const startButtonAnimation = () => {
  let distX = currX - prevX;
  let distY = currY - prevY;

  if (distX < 3 && distX > -3 && distY < 3 && distY > -3) {
    watchButtonRef.value.style.transform = `translate3d(${distX * 0.3}px, ${
      distY * 0.3
    }px, 0)`;
  }
};

const endButtonAnimation = () => {
  watchButtonRef.value.style.left = 0 + "px";
  watchButtonRef.value.style.top = 0 + "px";
};

const startTitleAnimation = () => {
  watchTitleRef.value.classList.remove("not_hovered");
  watchTitleRef.value.classList.add("hovered");
};
const endTitleAnimation = () => {
  watchTitleRef.value.classList.remove("hovered");
  watchTitleRef.value.classList.add("not_hovered");
};

const endAnimation = () => {
  endButtonAnimation();
  endTitleAnimation();
};
</script>
<template>
  <button
    class="watch_button"
    @mousemove="startButtonAnimation"
    @mouseover="startTitleAnimation"
    @mouseleave="endAnimation"
    ref="watchButtonRef"
  >
    <span class="watch_title_container">
      <span class="watch_title" ref="watchTitleRef">watch smth</span>
    </span>
  </button>
</template>

<style scoped>
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
  position: relative;
  cursor: pointer;
}

.watch_title_container {
  height: 20px;
  display: flex;
  overflow: hidden;
}

.watch_title.hovered {
  animation: slideUp 0.3s ease-in;
}

@keyframes slideUp {
  0% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-100%);
  }
  51% {
    transform: translateY(100%);
  }
  100% {
    transform: translateY(0%);
  }
}

.watch_title.not_hovered {
  animation: slideDown 0.3s ease-in;
}

@keyframes slideDown {
  0% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(100%);
  }
  51% {
    transform: translateY(-100%);
  }
  100% {
    transform: translateY(0%);
  }
}
</style>
