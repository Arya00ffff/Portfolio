<script setup>
import LoadingAnimation from './LoadingAnimation.vue'
import Background from './Background.vue'
import LightMode from './LightMode.vue'
import Skills from './Skills.vue'
import Career from './Career.vue'
import '@/assets/Main.css'
import { ref } from 'vue'
import Iconrow from './iconrow.vue'

const isLightMode = ref(false)
const contentVisible = ref(false)

function toggleLightMode() {
  isLightMode.value = !isLightMode.value
  document.body.classList.toggle('light-mode', isLightMode.value)
}

function handleAnimationStart() {
  contentVisible.value = true
  window.scrollTo(0, 0) 
}
</script>

<template>
  <LoadingAnimation @animationStart="handleAnimationStart" />
  <Background />
  <div :class="['main-content', { 'content-slide-up': contentVisible }]">
    <div class="row-center">
      <div class="left">
        <h1 style="font-size: 18px; font-weight: bold;"> <i class="fa-solid fa-location-dot" style="margin-right: 6px;"></i>Germany, Berlin</h1>
      </div>
      <div class="right">
        <LightMode @toggleLightMode="toggleLightMode" />
      </div>
    </div>
    <div class="image-row">
      <img src="@/assets/arya.png" alt="Arya's Avatar" height="480" width="347" class="bunnyPic"/>
      <div class="image-text">
        <h3 style="font-size: 25px; font-weight: 500;position: relative; bottom: -40px;">I'm Arya, and I like </h3>
        <h1 style="font-size: 70px;">
          Building pixel-perfect<br>
          <span :class="isLightMode ? 'gay-gradient-text' : 'trans-gradient-text'">Interactive</span> apps🌈
        </h1>
        <h2>Web-Developer</h2>
        <br><br>
        <Iconrow />
      </div>
    </div>

    <div class="career-container">
      <h1 style="text-align: center; margin-top: 70px;">Career</h1>
      <Career />
    </div>
    <div> 
      <h1 style="text-align: center; margin-top: 70px; margin-bottom: 30px;">Skills</h1>
    </div>
   <Skills />
    <br>
    <br><br><br>
  </div>
  <div class="footer">
      <p>© 2025 Arya. All rights reserved.</p>
    </div>
</template>

