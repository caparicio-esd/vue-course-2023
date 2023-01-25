<template>
  <div class="todo_app">
    <div class="todo_app_holder">
      <TodoHeader :todos="todos"></TodoHeader>
      <TodoMain :todos="todos"></TodoMain>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue"
import TodoHeader from "./components/TodoHeader.vue"
import TodoMain from "./components/TodoMain.vue"

const todos = ref([
  { title: "learn vue", isDone: true },
  { title: "do groceries", isDone: false },
  { title: "have lunch with mama", isDone: false },
])
</script>

<style lang="sass" scoped>
@import "/src/assets/mixins"
.todo_app
  @include f_body
  @apply min-h-screen bg-yellow-400 flex flex-col
  .todo_app_holder
    @apply h-full container mx-auto px-4 flex-1 flex flex-col
</style>
