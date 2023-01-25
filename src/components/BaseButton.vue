<template>
  <button class="button">{{ props.content }}</button>
</template>

<script setup>
const props = defineProps({
  content: String,
})
</script>

<style lang="sass" scoped>
@import "/src/assets/mixins"
.button
    @include f_title_base
    @apply bg-purple-500 border-2 border-purple-500 text-white
    @apply uppercase px-4 py-3 rounded-lg
    @apply hover:bg-purple-600 hover:border-purple-600 transition-colors duration-300
</style>
