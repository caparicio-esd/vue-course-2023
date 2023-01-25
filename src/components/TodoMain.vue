<template>
  <main class="main">
    <section class="todos">
      <Todo :todo="props.todos[0]"></Todo>
      <Todo :todo="props.todos[1]"></Todo>
      <Todo :todo="props.todos[2]"></Todo>
    </section>
    <div class="add_new">
      <BaseButton content="Add new"></BaseButton>
    </div>
  </main>
</template>

<script setup>
import BaseButton from "./BaseButton.vue"
import Todo from "./Todo.vue"

const props = defineProps({
  todos: Array,
})
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
