<script setup lang="ts">

import {onMounted, onUnmounted, ref} from "vue";

const x = ref(0)
const y = ref(0)

const handleMouseMove = (event: MouseEvent) => {
  x.value = event.pageX;
  y.value = event.pageX;
}

onMounted(() => {
  window.addEventListener('mousemove', handleMouseMove)
})

onUnmounted(() => {
  window.removeEventListener('mousemove', handleMouseMove)
})
</script>

<template>
  <div>
    <span>x:{{x}} y:{{y}}</span>
  </div>
</template>

<style scoped>

</style>