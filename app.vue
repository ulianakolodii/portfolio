<script setup lang="ts">
import navMenu from "./components/navMenu.vue";
import photoPreview from "./components/photoPreview.vue";
import mainTitle from "./components/mainTitle.vue";
</script>

<template>
  <div class="main_container"><navMenu /><mainTitle /><photoPreview /></div>
</template>

<style>
@import "./utilities/reset.css";
@import "./utilities/common.css";

.main_container {
  height: 100%;
  background-color: var(--general-bg-color);
}
</style>
