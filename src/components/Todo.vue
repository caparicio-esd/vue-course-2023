<template>
  <article
    class="todo"
    :class="classes"
    :style="styles"
  >
    <h4>{{ props.todo.title }}</h4>
    <div class="ctas">
      <div
        class="done"
        v-if="!props.todo.isDone"
        @click="toggleTodo(props.idx)"
      >
        <CheckCircleIcon />
      </div>
      <div
        class="undone"
        v-else
        @click="toggleTodo(props.idx)"
      >
        <CheckCircleIcon />
      </div>
      <div
        class="remove"
        @click="removeTodo(props.id)"
      >
        <XCircleIcon />
      </div>
    </div>
  </article>
</template>

<script setup>
import { CheckCircleIcon } from "@heroicons/vue/24/solid"
import { XCircleIcon } from "@heroicons/vue/24/solid"
import { computed, inject } from "vue"

const props = defineProps({
  todo: Object,
  idx: Number,
})
const { toggleTodo, removeTodo } = inject("todoData")
const classes = computed(() => ({
  done: props.todo.isDone,
}))
const styles = computed(() => ({
  backgroundColor: props.todo.isDone ? "pink" : "",
  border: "1px solid salmon",
  transform: props.todo.isDone ? "rotate(5deg)" : "",
}))
</script>

<style lang="sass" scoped>
@import "/src/assets/mixins"

.todo
    @apply flex justify-between
    h4
        @include f_title_base
    .ctas
        @apply flex gap-2
        .done
            @apply cursor-pointer h-6 w-6 text-blue-500
        .undone
            @apply cursor-pointer h-6 w-6 text-gray-300
        .remove
            @apply cursor-pointer h-6 w-6 text-red-500
    &.done
        h4
            @apply line-through
</style>
