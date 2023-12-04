<script setup lang="ts">

import {onMounted, ref} from "vue";

const input = ref<HTMLInputElement>()
const name = ref<string>('jun')

onMounted(() => {
  input.value?.focus()
  console.log(input.value?.value)
})
</script>

<template>
  <input ref="input" v-model="name"/>
</template>

<style scoped>

</style>