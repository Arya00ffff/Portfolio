<script setup>
import LoadingAnimation from './LoadingAnimation.vue'
import Background from './Background.vue'
import LightMode from './LightMode.vue'
import { ref } from 'vue'

const isLightMode = ref(false)
const contentVisible = ref(false)

function toggleLightMode() {
  isLightMode.value = !isLightMode.value
  document.body.classList.toggle('light-mode', isLightMode.value)
}

function handleAnimationStart() {
  contentVisible.value = true
}
</script>

<template>
  <LoadingAnimation @animationStart="handleAnimationStart" />
  <Background />
  <div :class="['main-content', { 'content-slide-up': contentVisible }]">
    <div class="row-center">
      <div class="left">
        <h1 style="font-size: 18px; font-weight: bold;">It's a me! Arya!</h1>
      </div>
      <div class="right">
        <LightMode @toggleLightMode="toggleLightMode" />
      </div>
    </div>
    <div class="image-row">
      <img src="@/assets/arya.png" alt="Arya's Avatar" height="480" width="347" class="bunnyPic"/>
      <div class="image-text">
        <h3 style="font-size: 25px; font-weight: 500;position: relative; bottom: -40px;">I'm Arya! , and I like </h3>
        <h1 style="font-size: 70px;">
          Building pixel-perfect<br>
          <span :class="isLightMode ? 'gay-gradient-text' : 'trans-gradient-text'">Interactive</span> apps🌈
        </h1>
        <h2>Web-Developer</h2>
        <br><br>
        <div class="icon-row">

          <a href="https://www.linkedin.com/">
            <i class="fa-brands fa-linkedin linkdin" ></i>  
          </a>
          <a href="http://github.com/arya00ffff/">
          <i class="fa-brands fa-github github"></i>
          </a>
          <a href="mailto:arya@gmail.com">
            <i class="fa-regular fa-envelope email" ></i> 
          </a>
          <i class="fa-brands fa-telegram telegram"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.main-content {
  transform: translateY(100vh);
  transition: transform 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}

.content-slide-up {
  transform: translateY(0);
}

.row-center {
  position: absolute;
  left: 0;
  width: 100vw;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

.left {
  margin-left: 20vw;
}

.right {
  margin-right: 20vw;
}

.bunnyPic{
  margin-left: 19.5vw;
  margin-top: 10vh;
  border-radius: 5px;
}

.image-row {
  display: flex;
  flex-direction: row;
  align-items: center;
}

.image-text {
  margin-left: 3vw;
  margin-bottom: 0vh;
}

.trans-gradient-text {
  font-size: 70px;
  font-weight: bold;
  background: linear-gradient(to right, #5BCEFA, #F5A9B8, #FFFFFF, #F5A9B8, #5BCEFA);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  display: inline-block;
}

.gay-gradient-text {
  font-weight: bold;
  background: linear-gradient(
    to right,
    #FF0018, /* Red */
    #FFA52C, /* Orange */
    #f5df14, /* Yellow */
    #008018, /* Green */
    #0000F9, /* Blue */
    #86007D  /* Violet */
  );
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  display: inline-block;
}
.icon-row {
  display: flex;
  gap: 16px; 
  align-items: center;
  font-size: 40px;
  cursor: pointer;
}

.linkdin {
  color: #bae6fd;
}
.linkdin:hover {
  color: #0072B1;
}
.light-mode .linkdin{
  color: #0385c7;
}
.light-mode .linkdin:hover{
  color:#065885;
}
.github {
color: #f0f6fc;
}
.github:hover {
  color: #333;
}
.light-mode .github{
  color: black;
}
.light-mode .github:hover{
  color: #333;
}
.email{
  color: #de5143;
}
.email:hover{
  color:#b04336;
}
.telegram{
  color:#24b3de;
}
.telegram:hover{
  color:#24A1DE;
}
</style>