<script setup lang="ts">
import {computed, reactive, Ref, ref} from "vue";
import HelloWorld from "./component/HelloWorld.vue";

const count: Ref<number> = ref(0);

export interface User {
  firstName: string,
  lastName: string,
  age: number
}

const user: User = reactive({
  firstName: 'John',
  lastName: 'Doe',
  age: 2
})

const fullName = computed<string>(() => `${user.firstName}  ${user.lastName}`)

const changeName : (name: string) => void = (name) => {
  user.firstName = name
}

changeName('jun')

</script>

<template>
  <body>
    <div>Count: {{ count }}</div>
    <button @click="count++">add Count</button>

    <div>FullName {{ fullName}}</div>

    <HelloWorld msg="HIHIHIHIHIHI" :user="user"/>
  </body>
</template>

<style scoped>
</style>
