<template>
  <div class="todo_app">
    <div class="todo_app_holder">
      <TodoHeader></TodoHeader>
      <TodoMain></TodoMain>
      <ModalWindow></ModalWindow>
    </div>
  </div>
</template>

<script setup>
import { provide, ref } from "vue"
import ModalWindow from "./components/ModalWindow.vue"
import TodoHeader from "./components/TodoHeader.vue"
import TodoMain from "./components/TodoMain.vue"

const todos = ref([
  { title: "learn vue", isDone: true },
  { title: "do groceries", isDone: false },
  { title: "have lunch with mama", isDone: false },
])
const addTodo = (todo) => {
  todos.value.push(todo)
}
const removeTodo = (idx) => {
  todos.value.splice(idx, 1)
}
const toggleTodo = (idx) => {
  todos.value[idx].isDone = !todos.value[idx].isDone
}

const openedModalWindow = ref(false)
const openModalWindow = () => {
  openedModalWindow.value = true
}
const closeModalWindow = () => {
  openedModalWindow.value = false
}
provide("todoData", {
  todos,
  openedModalWindow,
  openModalWindow,
  closeModalWindow,
  addTodo,
  removeTodo,
  toggleTodo,
})
</script>

<style lang="sass" scoped>
@import "/src/assets/mixins"
.todo_app
  @include f_body
  @apply min-h-screen bg-yellow-400 flex flex-col
  .todo_app_holder
    @apply h-full container mx-auto px-4 flex-1 flex flex-col
</style>
