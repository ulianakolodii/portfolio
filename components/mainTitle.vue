<script setup lang="ts"></script>
<template>
  <div class="main_text_container">
    <div class="main_title_container">
      <span class="main_title"
        ><span class="title_first_line">I MAKE IT</span>
        <span>BEAUTIFUL</span></span
      >
    </div>
    <div class="main_description_container">
      <span class="main_description"
        ><span class="description_dirst_line">motivated and enthusiastic</span> code-lover, looking for her first commercial
        project and opportunity to be useful.</span
      >
    </div>
  </div>
</template>
<style>
.main_text_container {
  position: absolute;
  width: 100%;
  display: flex;
  flex-direction: column;
  margin-top: 300px;
}

.main_title_container {
  width: 100%;
  display: flex;
  justify-content: center;
}

.main_title {
  font-family: var(--general-font);
  font-size: 130px;
  line-height: 0.8;
  letter-spacing: -0.07em;
  text-transform: uppercase;
  display: flex;
  flex-direction: column;
}
.title_first_line {
  margin-left: -136px;
}

.main_description_container {
  width: 100%;
  display: flex;
  justify-content: flex-end;
  margin-top: 100px;
  margin-left: -230px;
}

.main_description {
  font-family: var(--general-font);
  width: 220px;
  line-height: 1.3em;
  text-align: justify;
}

.description_dirst_line{
  margin-left: 20px;
}
</style>
