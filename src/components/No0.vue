<script setup lang="ts">

</script>

<template>
  <div class="box" relative h-20 w-20 rounded-2xl ring ring-2 />
</template>

<style scoped>
.box {
  overflow: hidden;
  z-index: 1;
}

.box::before {
  z-index: -2;
  content: '';
  position: absolute;
  width: 200%;
  height: 200%;
  background: orange;
  top: 50%;
  left: 50%;
  transform-origin: 0 0;
  animation: rotation 1s linear infinite;
}

.box::after {
  z-index: -1;
  content: '';
  background: currentColor;
  position: absolute;
  width: calc(100% - 6px);
  height: calc(100% - 6px);
  left: 3px;
  top: 3px;
  border-radius: 1rem;
}

@keyframes rotation {
  to {
    transform: rotate(1turn);
  }
}
</style>
