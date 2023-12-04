<script setup lang="ts">
import {ref} from "vue";

interface User {
  id: number,
  name: string,
  username: string,
  email: string,
  address: {
    street: string,
    suite: string,
    city: string
    zipcode: string,
    geo: {
      lat: number,
      lng: number
    }
  },
  phone: string,
  website: string,
  company: {
    name: string,
    catchPhrase: string,
    bs: string
  }
}

const users = ref<User[]>([])

const fetchUsers = async (): Promise<User[]> => {
  const res: Response = await fetch("https://jsonplaceholder.typicode.com/users")
  users.value = await res.json()
  console.log(res)

  return users.value
}

fetchUsers()
</script>

<template>
  <div v-for="user in users" :key="user.id">
    {{ user.name }}
    {{ user.username }}
    {{ user.email }}
    {{ user.phone }}
    <hr>
  </div>
</template>

<style scoped>

</style>