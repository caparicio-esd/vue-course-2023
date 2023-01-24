<template>
  <main class="main">
    <section class="todos">
      <Todo></Todo>
      <Todo></Todo>
      <Todo></Todo>
      <Todo></Todo>
      <Todo></Todo>
      <Todo></Todo>
      <Todo></Todo>
    </section>
    <div class="add_new">
      <BaseButton></BaseButton>
    </div>
  </main>
</template>

<script setup>
import BaseButton from "./BaseButton.vue"
import Todo from "./Todo.vue"
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
