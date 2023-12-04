<script setup lang="ts">
import {User} from "../App.vue"
import {Ref, ref} from "vue";

interface Props {
  msg: string
  user: User
}

interface Emits {
  (event: string, firstName: Ref<string>): void
}

defineProps<Props>();

let emit = defineEmits<Emits>();

const changeName = () => {
  emit("changeName", firstName)
}

const firstName = ref<string>()
</script>

<template>
  <div>
    <h1>{{msg}}</h1>
    <div>fullName: {{`${user.firstName} ${user.lastName}`}}</div>
    <input v-model="firstName"> <br>
    <button @click="changeName">ChangeName</button>
  </div>
</template>

<style scoped>

</style>