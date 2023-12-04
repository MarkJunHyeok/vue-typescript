<script setup lang="ts">
const handleChange = (event: Event, comment: string) => {
  console.log((event.target as HTMLInputElement).value)
  console.log(comment)
}
</script>

<template>
  <input @change="handleChange($event, `event야호`)" />
</template>

<style scoped>

</style>