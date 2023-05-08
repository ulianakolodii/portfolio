<script setup lang="ts"></script>
<template>
  <div class="photos_container">
    <div class="top_photo_container">
      <div class="photo_wrapper">
        <img
          class="top_photo"
          src="https://i.pinimg.com/564x/5f/78/35/5f7835335f71c0701d3670f040f54453.jpg"
        />
      </div>
    </div>
    <div class="middle_photo_container">
      <div class="middle_photo_wrapper">
        <img
          class="middle_photo"
          src="https://i.pinimg.com/564x/96/e4/0e/96e40e10bf126ef36eafe0335f911828.jpg"
        />
      </div>
    </div>
    <div class="bottom_photo_container">
      <div class="photo_wrapper">
        <img
          class="bottom_photo"
          src="https://i.pinimg.com/564x/76/29/35/76293509ec5e4f3ca7320e972f923725.jpg"
        />
      </div>
    </div>
  </div>
</template>
<style>
.photos_container {
  display: flex;
  flex-direction: column;
  max-width: 100vw;
}
.photo_wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 480px;
  height: 320px;
  overflow: hidden;
  border-radius: 100vw;
}

.top_photo_container {
  width: 100%;
  display: flex;
  justify-content: center;
  margin-top: -50px;
  margin-left: -0px;
}

.middle_photo_wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 320px;
  height: 320px;
  overflow: hidden;
  border-top-left-radius: 100vw;
  border-bottom-left-radius: 100vw;
}
.middle_photo_container {
  width: 100%;
  display: flex;
  justify-content: flex-end;
}

.bottom_photo_container {
  padding-left: 50px;
}

img {
  width: 480px;
}
</style>
