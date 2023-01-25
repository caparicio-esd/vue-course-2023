<template>
  <main class="main">
    <section
      class="todos"
      v-if="todos.length > 0"
    >
      <Todo
        v-for="(todo, i) in todos"
        :key="i"
        :todo="todo"
        :idx="i"
      ></Todo>
    </section>
    <div
      class="no_todos"
      v-else
    >
      No todos available
    </div>
    <div class="add_new">
      <BaseButton
        content="Add new"
        @click.prevent="openModalWindow"
      ></BaseButton>
    </div>
  </main>
</template>

<script setup>
import BaseButton from "./BaseButton.vue"
import Todo from "./Todo.vue"
import { inject } from "vue"

const { todos, openModalWindow } = inject("todoData")
</script>

<style lang="sass" scoped>
.main
    @apply bg-white px-6 py-12 flex-1 rounded-t-3xl
    .todos
        @apply flex flex-col divide-y-2
        > *
            @apply py-4
    .add_new
        @apply fixed bottom-4 right-4
</style>
