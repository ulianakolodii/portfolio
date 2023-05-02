<script setup lang="ts">
import logo from "./logo.vue";
import menuButton from "./menuButton.vue";
import watchButton from "./watchButton.vue";
</script>

<template>
  <div class="nav_container">
    <logo />
    <div class="menu_container">
      <watchButton />
      <menuButton />
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
</style>
