<script setup lang="ts"></script>
<template>
  <button class="watch_button">
    <span class="watch_title_container">
      <span class="watch_title">watch smth</span>
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

/* .watch_title {
  transition: transform 0.2s linear;
} */

.watch_button:hover .watch_title {
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

.watch_button .watch_title {
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
