<template>
  <div
    class="modal"
    :class="classes"
  >
    <div class="modal_holder">
      <h3>Contenido del modal</h3>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Exercitationem
        magnam, inventore repellendus laudantium corrupti quidem itaque delectus
        maiores perspiciatis at debitis officia consequatur assumenda
        voluptatibus, atque accusantium ullam, hic cum!
      </p>
      <form>
        <div class="form_control">
          <label for="new_todo">Add Todo</label>
          <input
            type="text"
            name="new_todo"
          />
        </div>
        <div class="form_control_buttons">
          <BaseButton
            content="Add todo"
            @click.prevent="closeModalWindow"
          ></BaseButton>
          <BaseButton
            content="Cancel"
            @click.prevent="closeModalWindow"
          ></BaseButton>
        </div>
      </form>
    </div>
  </div>
</template>

<script setup>
import { computed, inject } from "vue"
import BaseButton from "./BaseButton.vue"

const { openedModalWindow, closeModalWindow } = inject("todoData")
const classes = computed(() => ({
  "!hidden": !openedModalWindow.value,
}))
</script>

<style lang="sass" scoped>
@import "/src/assets/mixins"
.modal
    @apply fixed top-0 left-0 w-full h-full
    @apply bg-black bg-opacity-80
    @apply flex justify-center items-center
    .modal_holder
        @apply bg-white p-6  w-[90%] max-w-[460px]
        h3
            @include f_title_lg()
        p
            @apply my-4
        form
            .form_control
                @apply flex flex-col gap-2
                label
                    @include f_title_base()
                    @apply block
                input
                    @apply block p-2 border border-gray-500 rounded-lg
            .form_control_buttons
                @apply flex gap-2 mt-2
</style>
