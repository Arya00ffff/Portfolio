<script setup>

</script>

<template>
  <div id="container"></div>
</template>

<style scoped>
#container {
  width: 100vw;
  height: 100vh;
  aspect-ratio: 1;
  position: fixed;
  top: 0;
  left: 0;
  margin: 0;
  z-index: -1;


  background:
    repeating-linear-gradient(to right, #292737 0 1px, transparent 1px 48px),
    repeating-linear-gradient(to bottom, #292737 0 1px, transparent 1px 48px);
}
</style>