<script setup lang="ts">
import navMenu from "./components/navMenu.vue";
</script>

<template>
  <div class="main_container"><navMenu /></div>
</template>

<style>
@import "./utilities/reset.css";
@import "./utilities/common.css";

.main_container {
  height: 100vh;
  background-color: var(--general-bg-color);
}
</style>
