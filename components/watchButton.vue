<script setup lang="ts">
import { ref } from "vue";
const watchTitleRef = ref();
const startButtonAnimation = () => {
  watchTitleRef.value.classList.remove("not_hovered");
  watchTitleRef.value.classList.add("hovered");
};
const endButtonAnimation = () => {
  watchTitleRef.value.classList.remove("hovered");
  watchTitleRef.value.classList.add("not_hovered");
};
</script>
<template>
  <button
    class="watch_button"
    @mouseover="startButtonAnimation"
    @mouseleave="endButtonAnimation"
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
}

.watch_title_container {
  height: 20px;
  display: flex;
  overflow: hidden;
}

.watch_title.hovered {
  animation: slideUp 0.2s ease-in;
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
  animation: slideDown 0.2s ease-in;
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
