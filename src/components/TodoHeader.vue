<template>
  <header class="header">
    <HeaderContent :todos="todos"></HeaderContent>
    <HeaderBar :todos="todos"></HeaderBar>
  </header>
</template>

<script setup>
import HeaderBar from "./HeaderBar.vue"
import HeaderContent from "./HeaderContent.vue"

const props = defineProps({
  todos: Array,
})
</script>

<style lang="sass" scoped>
.header
    @apply flex flex-col gap-4 py-8 px-6
</style>
