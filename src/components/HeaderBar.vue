<template>
  <div class="header_bar">
    <div
      class="header_tooltip"
      :style="tooltipStyles"
    >
      {{ todosRate }}%
    </div>
    <div class="header_bar_bg"></div>
    <div
      class="header_bar_completed"
      :style="barStyles"
    ></div>
  </div>
</template>

<script setup>
import { computed, inject } from "vue"

const { todos } = inject("todoData")
const todosDone = computed(
  () => todos.value.filter((todo) => todo.isDone).length,
)
const todosRate = computed(() =>
  ((todosDone.value / todos.value.length) * 100).toFixed(2),
)
const barStyles = computed(() => ({
  width: todosRate.value + "%",
}))
const tooltipStyles = computed(() => ({
  left: todosRate.value + "%",
}))
</script>

<style lang="sass" scoped>
.header_bar
    @apply relative h-1 rounded-full my-2

    .header_tooltip
        @apply absolute top-full -translate-x-1/2 translate-y-1 left-0
        @apply bg-black text-white text-xs px-2 py-1
        @apply transition-all duration-300
    .header_bar_bg
        @apply absolute top-0 left-0 w-full h-full
        @apply bg-yellow-900 bg-opacity-25
    .header_bar_completed
        @apply absolute top-0 left-0 w-1/3 h-full
        @apply bg-yellow-900 bg-opacity-25
        @apply transition-transform duration-300
</style>
