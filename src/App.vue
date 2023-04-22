<script setup lang="ts">
import { reactive, ref } from 'vue'
const newTodo = ref()
const newTodoHandler = () => {
  console.log(newTodo.value)
}
</script>

<template>
  <section class="todoapp">
    <header class="header">
      <h1>todos</h1>
      <input class="new-todo" autofocus placeholder="What needs to be done?" @change="" />
    </header>
  </section>
</template>

<style scoped>
@import 'https://unpkg.com/todomvc-app-css@2.4.1/index.css';
</style>
