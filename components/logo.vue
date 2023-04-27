<script setup>
const firstLineRef = ref(null);
const secondLineRef = ref(null);

const startLogo = () => {
  firstLineRef.value.classList.remove("running-right");
  firstLineRef.value.classList.add("running-left");
  secondLineRef.value.classList.remove("running-left");
  secondLineRef.value.classList.add("running-right");
};

const endLogo = () => {
  firstLineRef.value.classList.remove("running-left");
  firstLineRef.value.classList.add("running-right");
  secondLineRef.value.classList.remove("running-right");
  secondLineRef.value.classList.add("running-left");
};
</script>

<template>
  <div class="logo" @mouseover="startLogo" @mouseleave="endLogo">
    <p class="first_line" ref="firstLineRef">PORT</p>
    <p class="second_line" ref="secondLineRef">FOLIO</p>
  </div>
</template>

<style scoped>
.logo {
  display: flex;
  flex-direction: column;
  margin-left: 40px;
  font-weight: 400;
  font-size: 30px;
  overflow: hidden;
}

.first_line {
  width: 80px;
}

.second_line {
  width: 90px;
  margin-left: 30px;
}

.running-left {
  animation: running-left 0.5s linear forwards;
}
.running-right {
  animation: running-right 0.5s linear forwards;
}

@keyframes running-left {
  0% {
    transform: translateX(0);
  }
  50% {
    transform: translateX(150%);
  }
  51% {
    transform: translateX(-150%);
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
    transform: translateX(-150%);
  }
  51% {
    transform: translateX(150%);
  }
  100% {
    transform: translateX(0);
  }
}
</style>
