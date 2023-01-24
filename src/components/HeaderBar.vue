<template>
  <div class="header_bar">
    <div class="header_bar_bg"></div>
    <div class="header_bar_completed"></div>
  </div>
</template>

<script setup></script>

<style lang="sass" scoped>
.header_bar
    @apply relative h-1 rounded-full my-2
    .header_bar_bg
        @apply absolute top-0 left-0 w-full h-full
        @apply bg-yellow-900 bg-opacity-25
    .header_bar_completed
        @apply absolute top-0 left-0 w-1/3 h-full
        @apply bg-yellow-900 bg-opacity-25
</style>
