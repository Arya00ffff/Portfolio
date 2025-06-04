<script setup>

</script>

<template>
  <button @click="$emit('toggleLightMode')" aria-label="Toggle light mode">

    <i class="fas fa-moon dark"></i>
    <i class="fa-solid fa-sun light"></i>
  </button>
</template>

<style scoped>
button {
  background-color: transparent;
  border: none;
  color: white;
  cursor: pointer;
  font-size: 28px;
  transition: transform 0.2s;
}
button:hover {
  transform: scale(1.1);
}
.light{
  display: none;
}
.light-mode .dark{
  display: none;
}
.light-mode .light{
  display: inline;
}
</style>
