<template>
  <div class="header_content">
    <h3>Mi todo list</h3>
    <p>
      Te quedan {{ todosDoneLength }}/{{ todosLength }} elementos por hacer. Un
      {{ todosRate }}% completado
    </p>
  </div>
</template>

<script setup>
import { computed, inject } from "vue"

const { todos } = inject("todoData")
const todosLength = computed(() => todos.value.length)
const todosDoneLength = computed(
  () => todos.value.filter((todo) => todo.isDone).length,
)
const todosRate = computed(() =>
  ((todosDoneLength.value / todosLength.value) * 100).toFixed(2),
)
</script>

<style lang="sass" scoped>
@import "/src/assets/mixins"
.header_content
    @apply flex items-baseline gap-2
    h3
        @include f_title_lg
    p
        @include f_sm
        @apply text-gray-600
</style>
