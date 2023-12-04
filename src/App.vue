<script setup lang="ts">
import {computed, reactive, Ref, ref, UnwrapRef} from "vue";

const count: Ref<number> = ref(0);

interface User {
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
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <body>
    <div>Count: {{ count }}</div>
  <button @click="count++">add Count</button>

  <div>FullName {{ fullName}}</div>
  </body>

  <main>
    <TheWelcome />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
