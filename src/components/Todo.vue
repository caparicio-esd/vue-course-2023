<template>
  <article class="todo">
    <h4>{{ props.todo.title }}</h4>
    <div class="ctas">
      <div class="done">
        <CheckCircleIcon />
      </div>
      <div class="undone">
        <CheckCircleIcon />
      </div>
      <div class="remove">
        <XCircleIcon />
      </div>
    </div>
  </article>
</template>

<script setup>
import { CheckCircleIcon } from "@heroicons/vue/24/solid"
import { XCircleIcon } from "@heroicons/vue/24/solid"

const props = defineProps({
  todo: Object,
})
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
