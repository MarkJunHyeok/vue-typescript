<script setup lang="ts">
import {User} from "../App.vue"

interface Props {
  msg: string
  user: User
}

interface Emits {
  (event: string, firstName: string): void
}

defineProps<Props>();

let emit = defineEmits<Emits>();

const changeName = () => {
  emit("changeName", "Jane")
}
</script>

<template>
  <div>
    <h1>{{msg}}</h1>
    <div>fullName: {{`${user.firstName} ${user.lastName}`}}</div>
    <button @click="changeName">ChangeName</button>
  </div>
</template>

<style scoped>

</style>