<template>
  <div class="header_content">
    <h3>Mi todo list</h3>
    <p>Te quedan 3/5 elementos por hacer. Un 76% completado</p>
  </div>
</template>

<script setup></script>

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
