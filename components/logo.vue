<script setup>
const firstLineRef = ref();
const secondLineRef = ref();

const startLogoAnimation = () => {
  firstLineRef.value.classList.remove("running-right");
  firstLineRef.value.classList.add("running-left");
  secondLineRef.value.classList.remove("running-left");
  secondLineRef.value.classList.add("running-right");
};

const endLogoAnimation = () => {
  firstLineRef.value.classList.remove("running-left");
  firstLineRef.value.classList.add("running-right");
  secondLineRef.value.classList.remove("running-right");
  secondLineRef.value.classList.add("running-left");
};
</script>

<template>
  <div
    class="logo"
    @mouseover="startLogoAnimation"
    @mouseleave="endLogoAnimation"
  >
    <div class="first_line">
      <p ref="firstLineRef">PORT</p>
    </div>
    <div class="second_line">
      <p ref="secondLineRef">FOLIO</p>
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

.first_line {
  width: 80px;
  overflow: hidden;
}

.second_line {
  width: 90px;
  margin-left: 30px;
  overflow: hidden;
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
