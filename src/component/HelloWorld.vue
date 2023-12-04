<script setup lang="ts">
import {User} from "../App.vue"

interface Props {
  msg: string
  user: User
}

defineProps<Props>();
</script>

<template>
  <div>
    <h1>{{msg}}</h1>
    <div>fullName: {{`${user.firstName} ${user.lastName}`}}</div>
  </div>
</template>

<style scoped>

</style>